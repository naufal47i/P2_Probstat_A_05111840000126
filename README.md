
# PRAKTIKUM PROBSTAT 2 2022  

#### Kelas   : Probabilitas dan Statistik A
#### Nama    : Muhammad Naufal Arieffaza
#### NRP     : 05111840000126

</br>


### Nomor 1 
Seorang peneliti melakukan penelitian mengenai pengaruh aktivitas A terhadap kadar saturasi oksigen pada manusia. Peneliti tersebut mengambil sampel sebanyak 9 responden. Pertama, sebelum melakukan aktivitas A, peneliti mencatat kadar saturasi oksigen dari 9 responden tersebut. Kemudian, 9 responden tersebut diminta melakukan aktivitas A. Setelah 15 menit, peneliti tersebut mencatat kembali kadar saturasi oksigen dari 9 responden tersebut. Berikut data dari 9 responden mengenai kadar saturasi oksigen sebelum dan sesudah melakukan aktivitas A

![soal 1](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/1.jpg)

Berdasarkan data pada tabel diatas, diketahui kadar saturasi oksigen dari responden ke-3 ketika belum melakukan aktivitas 𝐴 sebanyak 67, dan setelah melakukan aktivitas 𝐴 sebanyak 70.

#### 1a
Carilah Standar Deviasi dari data selisih pasangan pengamatan tabel diatas

</br>

Langkah pertama penyelesaian adalah memasukkan semua data yang ada pada tabel pada sebuah variabel sebagai berikut
```
before <- c(78, 75, 67, 77, 70, 72, 28, 74, 77)
```
```
after <- c(100, 95, 70, 90, 90, 90, 89, 90, 100)
```
Setelah dimasukkan semua datanya, maka dilakukan cek data menggunakan `data.frame` yaitu
```
my_data <- data.frame(
    group = rep(c("sebelum", "sesudah"), each = 9),
    saturation = c(before, after)
)
```
Setelah itu dilihat hasil framenya sebagai berikut
```
print(my_data)
```
![1a](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/1a.jpg)

Selanjutnya mencari standar deviasinya. Standar deviasi sebelum aktivitas adalah
```
SD_before <- sd(before)
SD_before
```
Maka hasilnya : 
</br>
![1a1](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/1a1.jpg)
</br>

Standar deviasi setelah aktivitas adalah
```
SD_after <-sd(after)
SD_after
```
Maka hasilnya : 
</br>
![1a2](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/1a2.jpg)

#### 1b
carilah nilai t (p-value)

</br>

Untuk mencari nilai t terutama p-value maka bisa menggunakan fungsi `t.test` yaitu sebagai berikut
```
t.test(before, after, alternative = "greater", var.equal = FALSE)
```
Maka hasilnya adalah: 
</br>

![1b](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/1b.jpg)

#### 1c
tentukanlah apakah terdapat pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen, sebelum dan sesudah melakukan aktivitas 𝐴 jika diketahui tingkat signifikansi 𝛼 = 5% serta H0 : “tidak ada pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen , sebelum dan sesudah melakukan aktivitas 𝐴”

</br>

Langkah pertama yaitu melihat hasil komparasi dua variabel berikut
```
var.test(before, after)
```
![1c](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/1c.jpg)

</br>

Selanjutnya, untuk melihat pengaruh jika tingkat signifikasi 5% dan tidak ada pengaruh yang signifikan secara statistika, maka adalah sebagai berikut
```
t.test(before, after, var.equal = TRUE)
```
![1c2](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/1c2.jpg)

</br>

Bisa dilihat bahwa mean dan convidence sama dengan 1b, yang berbeda adalah p-value dan df. Sehingga tidak memiliki pengaruh yang signifikan secara statistika

### Nomor 2
Diketahui bahwa mobil dikemudikan rata-rata lebih dari 20.000 kilometer per tahun. Untuk menguji klaim ini, 100 pemilik mobil yang dipilih secara acak diminta untuk mencatat jarak yang mereka tempuh. Jika sampel acak menunjukkan rata-rata 23.500 kilometer dan standar deviasi 3900 kilometer. (Kerjakan menggunakan 2 library seperti referensi pada modul).

#### 2a
Apakah Anda setuju dengan klaim tersebut?

*Setuju*

#### 2b
Jelaskan maksud dari output yang dihasilkan!

![2b](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/2b.jpg)

Diketahui n = 100, Rata-Rata (X̄) = 23500, dan standar deviasi(σ) = 3900
Maka null hipotesis adalah 
```
H0 : μ = 20000
```
Alternatif hipotesisnya yaitu
```
H1 : μ > 20000
```

#### 2c
Buatlah kesimpulan berdasarkan P-Value yang dihasilkan!


Untuk mencari nilai z nya yaitu 
</br>
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/2c.png)

Lalu mencari nilai p-value nya sebagai berikut
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/2c1.png)
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/2c2.png)

Sehingga kesimpulan yang didapat adalah bahwa mobil dikemudikan rata-rata lebih dari 20.000 kilometer per tahun

### Nomor 3
Diketahui perusahaan memiliki seorang data analyst ingin memecahkan permasalahan pengambilan keputusan dalam perusahaan tersebut. Selanjutnya didapatkanlah data berikut dari perusahaan saham tersebut.
</br>
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/3.png)
Dari data diatas berilah keputusan serta kesimpulan yang didapatkan dari hasil diatas. Asumsikan nilai variancenya sama, apakah ada perbedaan pada rata-ratanya (α= 0.05)? Buatlah :

#### 3a
H0 dan H1
dilakukan perhitungan H0 sebagai berikut
</br>
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/3a.png)
</br>
dilakukan perhitungan H1 sebagai berikut
</br>
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/3a2.png)

#### 3b
Hitung Sampel Statistik
Penghitungan dilakukan sebagai berikut
```
tsum.test(mean.x=3.64, s.x = 1.67, n.x = 19, mean.y =2.79 , s.y = 1.32, n.y = 27, alternative = "greater", var.equal = TRUE)
```
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/3b.png)


#### 3c
Lakukan Uji Statistik (df =2)

Melakukan install library `mosaic`
```
install.packages("mosaic")
library(mosaic)
```

```
plotDist(dist='t', df=2, col="blue")
```
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/3c.png)

#### 3d
Nilai kritikal
Adapun untuk mendapatkan nilai kritikal bisa menggunakan `qchisq` dengan `df=2` sesuai soal sebelumnya

![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/3d.png)

#### 3e
Keputusan

Teori keputusan adalah teori formal pengambilan keputusan di bawah ketidakpastian. 
Aksinya adalah : `({a}_{a∈A})`
Kemungkinan konsekuensi : `({c}_{c∈C})` (tergantung pada keadaan dan tindakan)
Maka keputusan dapat dibuat dengan `t.test`

#### 3f
Kesimpulan
Kesimpulan yang didapatkan yaitu perbedaan rata-rata yang terjadi tidak ada jika dilihat dari uji statistik dan akan ada tetapi tidak signifikan jika dipengaruhi nilai kritikal.

### Nomor 4
Seorang Peneliti sedang meneliti spesies dari kucing di ITS . Dalam penelitiannya ia mengumpulkan data tiga spesies kucing yaitu kucing oren, kucing hitam dan kucing putih dengan panjangnya masing-masing.
Jika : diketahui dataset https://intip.in/datasetprobstat1
H0 : Tidak ada perbedaan panjang antara ketiga spesies atau rata-rata panjangnya sama. Maka Kerjakan atau Carilah:
#### 4a
Buatlah masing masing jenis spesies menjadi 3 subjek "Grup" (grup 1,grup 2,grup 3). Lalu Gambarkan plot kuantil normal untuk setiap kelompok dan lihat apakah ada outlier utama dalam homogenitas varians.
</br>
Langkah pertama mengambil data dari link yang telah disediadakan

```
myFile  <- read.table(url("https://rstatisticsandresearch.weebly.com/uploads/1/0/2/6/1026585/onewayanova.txt")) 
dim(myFile)
head(myFile)
```

Selanjutnya membuat myFile menjadi group 
```
myFile$Group <- as.factor(myFile$Group)
myFile$Group = factor(myFile$Group,labels = c("Kucing Oren","Kucing Hitam","Kucing Putih"))
```

Setelah itu, dicek apakah dia menyimpan nilai di groupnya
```
class(myFile$Group)
```

Lalu bagi tiap valuer menjadi 3 bagian ke 3 grup
```
group1 <- subset(myFile, Group=="Kucing Oren")
group2 <- subset(myFile, Group=="Kucing Hitam")
group3 <- subset(myFile, Group=="Kucing Putih")
```
#### 4b
carilah atau periksalah Homogeneity of variances nya , Berapa nilai p yang didapatkan? , Apa hipotesis dan kesimpulan yang dapat diambil ?

Mencari Homogeneity of variances bisa menggunakan command sebagai berikut
```
bartlett.test(Length~Group, data=dataoneway)
```
Setelah di jalankan maka nilai p-value = 0.8054. 
Kesimpulan yang didapatkan yaitu Bartlett's K-squared memiliki nilai sebesar 0.43292 dan df bernilai 2
#### 4c

```
qqnorm(group1$Length)
qqline(group1$Length)
```

![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/4c.png)

#### 4d
Dari Hasil Poin C, Berapakah nilai-p ? , Apa yang dapat Anda simpulkan dari H0?
Setelah di jalankan maka nilai p-value = 0.8054. 

#### 4e
Verifikasilah jawaban model 1 dengan Post-hoc test Tukey HSD, dari nilai p yang didapatkan apakah satu jenis kucing lebih panjang dari yang lain? 3 Jelaskan.
Langkah pertama adalah menggunakan command ANOVA
```
model1 <- lm(Length~Group, data=myFile)
```
Selanjutnya menggunakan command 
```
anova(model1)
```
Lalu menggunakan model Post-hoc Tukey HSD sebagai berikut
```
TukeyHSD(aov(model1))
```

#### 4f
Visualisasikan data dengan ggplot2
```
library(ggplot2)
ggplot(dataoneway, aes(x = Group, y = Length)) + geom_boxplot(fill = "grey80", colour = "black") + scale_x_discrete() + xlab("Treatment Group") +  ylab("Length (cm)")
```


### Nomor 5
Data yang digunakan merupakan hasil eksperimen yang dilakukan untuk mengetahui pengaruh suhu operasi (100˚C, 125˚C dan 150˚C) dan tiga jenis kaca pelat muka (A, B dan C) pada keluaran cahaya tabung osiloskop. Percobaan dilakukan sebanyak 27 kali dan didapat data sebagai berikut: Data Hasil Eksperimen. Dengan data tersebut:
#### 5a
Buatlah plot sederhana untuk visualisasi data

Run semua library yang diperlukan
```
install.packages("multcompView")
library(readr)
library(ggplot2)
library(multcompView)
library(dplyr)
```

Selanjutnya membaca file GTL.csv dari documents
```
GTL <- read_csv("GTL.csv")
head(GTL)
```
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/5a.png)

</br>

Lakukan observasi pada data
```
str(GTL)
```
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/5a1.png)
</br>

Selanjutnya lakukan viasualisasi menggunakan simple plot yaitu sebagai berikut
```
qplot(x = Temp, y = Light, geom = "point", data = GTL) +
  facet_grid(.~Glass, labeller = label_both)
```
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/5a2.png)

#### 5b
Lakukan uji ANOVA dua arah
Langkah pertama adalah membuat variabel as factor sebagai ANOVA
```
GTL$Glass <- as.factor(GTL$Glass)
GTL$Temp_Factor <- as.factor(GTL$Temp)
str(GTL)
```
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/5b.png)

</br>

Selanjutnya melakukan analisis of variance (aov) yaitu sebagai berikut 
```
anova <- aov(Light ~ Glass*Temp_Factor, data = GTL)
summary(anova)
```
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/5b2.png)

#### 5c
Tampilkan tabel dengan mean dan standar deviasi keluaran cahaya untuk setiap perlakuan (kombinasi kaca pelat muka dan suhu operasi)

Menggunakan `group_by` lalu melakukan `summarise` sesuai mean dan standar deviasi yang berlaku sehingga scriptnya adalah sebagai berikut
```
data_summary <- group_by(GTL, Glass, Temp) %>%
  summarise(mean=mean(Light), sd=sd(Light)) %>%
  arrange(desc(mean))
print(data_summary)
```
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/5c.png)

</br>

#### 5d
Lakukan uji Tukey

Menggunakan fungsi `TukeyHSD` sebagai berikut
```
tukey <- TukeyHSD(anova)
print(tukey)
```
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/5d.png)
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/5d1.png)

#### 5e
Gunakan compact letter display untuk menunjukkan perbedaan signifikan antara uji Anova dan uji Tukey

Awalnya yaitu membuat compact letter display sebagai berikut
```
tukey.cld <- multcompLetters4(anova, tukey)
print(tukey.cld)
```
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/5e.png)

</br>
Tambahkan compact letter display tersebut ke tabel dengan means(rata-rata) dan sd

```
cld <- as.data.frame.list(tukey.cld$`Glass:Temp_Factor`)
data_summary$Tukey <- cld$Letters
print(data_summary)
```
![image](https://github.com/naufal47i/P2_Probstat_A_05111840000126/blob/main/Foto/5e2.png)
