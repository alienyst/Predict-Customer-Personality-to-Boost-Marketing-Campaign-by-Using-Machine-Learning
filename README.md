# Predict Customer Personality to Boost Marketing Campaign by Using Machine Learning

## Latar Belakang

Setiap orang memiliki tipe kepribadian dan perilaku yang berbeda untuk melakukan pembelian yang tentunya dipengaruhi oleh berbagai banyak hal. Perusahaan perlu melakukan analisis terperinci tentang pelanggan yang sekiranya ideal bagi perusahaan agar menaikkan performa dan menyasar customers yang tepat agar dapat bertransaksi di platform perusahaan. Dengan memanfaatkan data historical marketing campaign dapat dilakukan penggalian insight data dengan membuat sebuah model prediksi kluster sehingga memudahkan perusahaan dalam membuat keputusan.

## Conversion Rate Analysis
Berdasarkan hasil EDA, berikut didapatkan beberapa karakteristik Customer yang memiliki conversion rate yang tinggi :

- Terlihat  bahwa  mayoritas customer berstatus marital 'yang mengikat', namun  secara CR justru 'hubungan yang tidak  mengikat yang lebih  tinggi’
- Secara  usia  mayoritas  pengguna  berumur 34 - 45, akan  tetapi  umur yang 18 - 34 yang memiliki CR yang lebih  tinggi/ merespon campaign
- Total Campaign 4 atau 3
- Tidak  memiliki  anak/bukan orang tua
- Pendidikan Tinggi yaitu  dari S1 - S3
- High Income yaitu  lebih  besar  dari 68.522.
- Total Spend lebih  besar  dari 1.045.500 atau Extravagant Customer
- Total Transaksi  lebih  dari 4 kali
- Mengunjungi Halaman Web antara 3-5 kali
- Nilai Recency dibawah 25
- Sangat masuk  akal  apabila yang memiliki income tinggi  akan  cenderung  merespon campaign di karenakan customer ini  biasanya  memiliki uang yang lebih  dengan  dibuktikan total spend yang lebih  tinggi  dengan total transaksi yang terbilang  sering, hal  ini  bisa  dilihat  dari  jumlah  kunjungan  ke  halaman web.

## Data Cleaning & Preprocessing
- Handling Missing Value dengan memberikan threatment imputasi median.
- Feature Selection, feature yang dipilih  adalah dengan  mengurangi  dimensi  seperti  lebih  memilih total campaign dibanding AcceptedCmp1, AcceptedCmp2 dst. Adapun feature yang dipilih  antara lain : Income , Recency, NumWebPurchases, Response, Jumlah_Anak, Is_Parent, Total_Spend, Total_Campaign, Total_Transaksi, Member_Duration, Conversion_Rate
- Handling Outliers menggunakan Teknik Z-Score. Sebelum  dilakukan  penangan outliers data berjumlah 2240, setelah  dilakukan  penangan data berkurang  menjadi 2222.
- Feature Encoding menggunakan OneHot Encoding dan OrdinalEncoding.
- Feature Standarization, nilai di beberapa feature memiliki  perbedaan  rentang  nilai yang sangat besar  sehingga  perlu  distandarisasi agar normal. Pada kolom yang tipe data numerical digunakan Teknik ‘StandardScaler' dan 'MinMax' untuk  beberapa  kolom  kategorikal.

## Data Modeling

Elbow method adalah Teknik yang digunakan  untuk  mencari  nilai k atau  jumlah  klaster yang paling optimal pada algoritma k-means dengan  melihat  siku. Adapun siku terletak pada k=3, Dengan kata lain nilai k yang paling Optimal adalah 3.

Silhoutte score adalah  ukuran  seberapa  mirip  suatu  titik data di dalam  klaster (kohesi) dibandingkan  dengan  klaster lain (pemisahan). Pada silhouette score diambil  nilai rata-rata tertinggi, Terlihat  bahwa k=2 adalah  nilai  tertinggi, tetapi  apabila  menggunakan  dua  klaster  rasanya terlalu  sedikit, oleh karena  itu  opsi  terbaik  adalah 3 klaster.


