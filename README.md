# Prediction Potensial Customer

| | Deskripsi |
| ----------- | ----------- |
| Dataset | [Bank Marketing](https://www.kaggle.com/datasets/dhirajnirne/bank-marketing) |
| Masalah | Dalam menjalankan bisnis, pemasaran memainkan peran penting dalam mendorong pertumbuhan perusahaan. Ini karena pemasaran berfungsi langsung dalam menjual produk. Dalam industri perbankan, tantangan pemasaran serupa juga ada, yaitu bagaimana meningkatkan penjualan produk perbankan. Meskipun industri perbankan memiliki data konsumen dan calon konsumen yang melimpah, mereka menghadapi keterbatasan sumber daya, baik dalam hal anggaran pemasaran maupun waktu. Oleh karena itu, penting untuk menentukan konsumen mana yang harus dihubungi terlebih dahulu, yaitu mereka yang memiliki kemungkinan terbesar untuk membeli produk. Jadi, pertanyaan yang muncul adalah **Bagaimana Memprediksi Kemungkinan Seseorang Membeli Produk?**|
| Solusi machine learning | Untuk mengatasi tantangan menentukan apakah seseorang akan membeli produk atau tidak, kita dapat memanfaatkan teknologi Machine Learning. Machine Learning memungkinkan kita untuk membuat prediksi tentang probabilitas seseorang melakukan pembelian berdasarkan berbagai informasi yang tersedia sebagai input. Proses ini melibatkan pengumpulan data relevan tentang konsumen, seperti riwayat pembelian, preferensi, demografi, dan perilaku online. Data ini kemudian dianalisis dan digunakan untuk melatih model Machine Learning. Model Machine Learning ini akan belajar dari pola dan hubungan dalam data historis untuk mengidentifikasi faktor-faktor kunci yang mempengaruhi keputusan pembelian. Setelah model dilatih, kita dapat menggunakannya untuk memprediksi apakah calon konsumen tertentu memiliki kemungkinan tinggi untuk membeli produk yang ditawarkan. Dengan demikian, perusahaan dapat mengalokasikan sumber daya pemasaran mereka dengan lebih efisien, fokus pada konsumen yang memiliki potensi tertinggi, dan meningkatkan tingkat konversi penjualan. Ini tidak hanya membantu dalam mengoptimalkan biaya dan waktu pemasaran, tetapi juga meningkatkan kepuasan pelanggan dengan menawarkan produk yang lebih relevan sesuai dengan kebutuhan mereka.|
| Metode pengolahan | Proses ini dimulai dengan mengolah data yang telah diberi label 0 (tidak membeli) dan 1 (membeli). Langkah berikutnya adalah mengembangkan dan memvalidasi model. Pengembangan model melibatkan eksperimen untuk menemukan parameter terbaik (*Tuning Parameters*), yang kemudian digunakan dalam proses pelatihan model. Setelah itu, dilakukan analisis validasi model untuk memastikan model sudah bekerja dengan baik. Jika model telah tervalidasi dengan memuaskan, langkah selanjutnya adalah menerapkan model tersebut (*Deployment*), dengan mencoba mengimplementasikannya dalam lingkungan **cloud**.|
| Arsitektur model | Arsitektur model ini menggunakan konsep Jaringan Saraf Tiruan yang terdiri dari tiga lapisan utama: input layer, hidden layer, dan output. Dalam model ini, lapisan dense ditambahkan dengan menggunakan jumlah unit yang ditentukan oleh hyperparameters["dense_unit"] dan diaktifkan dengan fungsi aktivasi ReLU. Selanjutnya, lapisan dropout ditambahkan dengan tingkat dropout yang ditentukan oleh hyperparameters["dropout_rate"] untuk mencegah overfitting. Lapisan output terdiri dari satu unit dengan fungsi aktivasi sigmoid untuk menghasilkan output biner. Model ini kemudian didefinisikan menggunakan tf.keras.Model dengan input dari input_features dan output dari lapisan sigmoid. Model dikompilasi dengan optimizer Adam yang memiliki learning rate yang ditentukan oleh hyperparameters["learning_rate"]. Loss function yang digunakan adalah BinaryCrossentropy, dan model dievaluasi menggunakan metrik binary_accuracy. |
| Metrik evaluasi | Metrik yang disediakan sebagai bahan evaluasi model adalah Example Count, False Positives, True Positives, False Negatives, True Negatives, dan yang utama yaitu Binary Accuracy |
| Performa model | Model menunjukkan performa yang sangat baik dengan metrik Binary Accuracy, mencapai 89,52% pada data pelatihan dan 89,43% pada data validasi. Hasil ini menunjukkan bahwa model memiliki akurasi yang mendekati 90% pada kedua set data, menandakan bahwa model bekerja dengan efektif tanpa mengalami *underfitting*. Kinerja model ini juga menunjukkan bahwa tidak ada masalah *overfitting*, karena selisih antara akurasi pelatihan dan validasi sangat kecil, hanya 0,09%. Perbedaan yang minim ini menunjukkan bahwa model dapat menggeneralisasi dengan baik dari data pelatihan ke data yang belum pernah dilihat sebelumnya. Dengan demikian, model ini telah mencapai performa yang sangat baik dan stabil pada kedua set data tersebut.|
| Opsi deployment | Pada proyek Machine Learning ini telah mencoba di deployment menggunakan sebuah platform Railway |
| Web app |[bankPurchase-Model](https://bank-marketing-production.up.railway.app/v1/models/purchase-model/metadata)|
| Monitoring | Pada proyek Machine Learning ini telah mencoba dimonitoring menggunakan Prometheus yang disinkronkan dengan Grafana untuk menghasilkan sebuah dashboard monitoring yang menarik. Dengan Menerapkan Grafana kita dapat melihat banyak informasi terkait proses deployment, salah satunya adalah Fluktuasi Penggunaan Memory RSS dari waktu ke waktu. |