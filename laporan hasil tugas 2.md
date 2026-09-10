# Laporan Interpretasi Hasil
## Analisis Network Pharmacology Metabolit Inonotus obliquus (Jamur Chaga) terhadap kanker kolorektal
Kita akan meneliti apakah senyawa yang terdapat pada jamur Chaga serta beberapa komponen tumbuhan lain dapat berinteraksi dengan sel kanker kolorektal.

Langkah pertama kita mencari gen kanker kolorektal di website OMIM. Setelah mendapat datanya, kita ambil data approved symbolnya, lalu kita bersihkan dengan “Remove Duplicate”. Dengan bantuan literatur, kita mengambil senyawa-senyawa yang diduga dapat berinteraksi dengan gen kanker kolorektal. Pada studi ini kita mengambil senyawa dari jamur Chaga dan juga dari senyawa-senyawa lain.

Kita kemudian ke PubChem dan mengambil data SMILE dari senyawa-senyawa obat tersebut. Masukkan data SMILE ke Swiss Target Prediction dan ambil “common name” dari file-file Excel tersebut. Buat sheet excel sendiri untuk tiap-tiap senyawa dan hapus kolom yang tertulis N/A. Buat sheet excel sendiri yang merupakan gabungan dari keenam senyawa obat, jangan lupa hapus duplikat. Buat juga excel sendiri yang bertuliskan nama dan termasuk dalam senyawa apa target-target tersebut.

Buat di file excel baru satu sheet yang berisi semua senyawa penyakit dan juga semua senyawa obat yang bersebelahan. Kemudian buat irisan dari kedua data tersebut menggunakan website Venny, dan juga buat gabungan antara senyawa penyakit dan obat.

Masukkan hasil irisan dari data penyakit dan data obat ke website String untuk kemudian mendapat visualisasi protein-protein interaction irisan dari penyakit dan obat. Setelah irisan, buat gabungan dari senyawa penyakit dan obat dalam satu column, lalu masukkan ke String untuk mendapat visualisasi protein-protein interaction gabungan. Jadi sekarang kita mempunyai dua file, irisan dan gabungan dari senyawa penyakit dan obat.

Langkah berikutnya adalah visualisasi data menggunakan aplikasi Cytoscape. Masukkan file gabungan data dan kita dapat melihat data gabungan yang masif. Kemudian lakukan analyze network untuk melihat data-data dari senyawa gabungan tersebut seperti degree, betweenness centrality, dan closeness centrality.

Kemudian aktifkan cytocluster dan gunakan untuk membuat cluster-cluster. Dalam studi ini terbentuk 13 cluster. Kita lalu membuat network dari cluster pertama. Network itu lalu kita analisis seperti biasa. Kita kemudian menghapus data-data analisis yang tidak kita butuhkan, dan sisakan degree, betweenness centrality, dan closeness centrality karena hanya data itu yang kita butuhkan.

Kita lalu ubah bentuk network menjadi lingkaran berdasarkan degree. Setelah disimpan, kita kembali ke main network. Dengan cytohubba kita ambil 20 data terpenting dari network tersebut. Rangking tertinggi pada network ini adalah EGFR. Kita kemudian membuka file irisan dan terdapat 9 nodes. Dengan Cytohubba didapatkan kalau node tertinggi adalah MTOR.

Kita kemudian melakukan enrichment analysis dengan ShinyGO. Top 20 senyawa yang kita dapatkan tadi kita masukkan ke dalam ShinyGO. Dari 20 senyawa tersebut yang menduduki posisi paling berpengaruh adalah “Prolactin Signaling Pathway”.

Kita lalu kembali ke String dan memasukkan 9 protein irisan yang tadi. Dari hasil analisis, kita akan mendownload biological process (gene ontology), molecular function (gene ontology), KEGG pathways, dan All Enriched Terms untuk kemudian divisualisasikan di Cytoscape. Kita buka file Enrichment KEGG dan mendapatkan 18 pathways.

Kita kemudian membuka file target-senyawa dan jangan lupa mengubah tanda di senyawa menjadi source node. Dan inilah network target-senyawa yang kita miliki. Kita juga membuka file string_interaction_irisan yang kita dapat di awal. Dan terakhir kita membuka file Enrichment KEGG yang berisi 18 pathways. Kita kemudian me-“merge” (menggabungkan) ketiga file tersebut dan inilah network yang kita miliki.

Kita kemudian pilih nodesnotes connected by selected edges. Selanjutnya kita memilih first neighborhood of selected nodes dan klik undirected. Kita lanjutkan dengan memilih new network dan from selected nodes, all edges. Dan inilah network pharmacology yang kita punya.

### Referensi
Molecular mechanisms of phytochemicals from Chaga Mushroom (Inonotus obliquus) against colorectal cancer: Insight from network pharmacology, molecular docking and bioinformatics — https://doi.org/10.3390/ijms26167664
