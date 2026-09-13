# Workflow Penelitian

Langkah-langkah dalam Network Pharmacology:
* Pencarian data target gen dengan OMIM
*	Setelah data dibersihkan, ambil data “Approved Symbol”-nya
*	Mencari senyawa potensial yang bisa berinteraksi dengan gen target penyakit dengan PubChem
*	Ambil SMILE-nya di PubChem
*	Ambil “Common Name”-nya di SwissTargetPrediction
*	Gabungkan semua Common Name/Target di Excel dan hapus setiap duplikat, beri nama sheet “All Target”
*	Gabungkan setiap target dan tulis senyawanya
*	Gabungkan Approved Symbol dan Common Name di Excel dan buat juga irisan Approved Symbol dan Common Name di Venny, setelah itu masukkan ke Excel
*	Masukkan file gabungan maupun irisan ke STRING-DB dan download visualisasinya untuk dianalisis di Cytoscape
*	Lakukan clustering dengan CytoCluster dan ranking node dengan CytoHubba
*	Melakukan enrichment analysis dengan ShinyGO menggunakan data dari top 20 union degree dan mendownload biological process, molecular function, KEGG pathways, dan all enrich terms
*	Memvisualisasikan network senyawa-target dengan Cytoscape
*	Merge (menggabungkan) network senyawa-target, irisan penyakit-senyawa, dan hasil enrichment KEGG
*	Membuat visualisasi dari hasil Merge

Langkah-langkah dalam Molecular Docking:
* Dari ranking tertinggi string_interaction_irisan.tsv, didapatkan protein target/reseptor yang paling signifikan adalah mTOR
*	Dari semua identifier mTOR, saya memilih 4JSX sebagai protein yang paling cocok untuk dilakukan molecular docking
*	Di SwissDock persiapkan ligan (Ergosterol Peroxide), 4JSX sebagai protein target, dan posisi ligan di protein yang sudah didapatkan di PrankWeb
*	Mulai lakukan Docking

# Hasil Network Pharmacology
![the_real_final_countdown_gambar](the_real_final_countdown_gambar.png)
# Hasil Molecular Docking
![visualisasi](visualisasi.png)
# Laporan Singkat
## Pendahuluan
Kita akan meneliti apakah senyawa yang terdapat pada jamur Chaga serta beberapa komponen tumbuhan lain dapat berinteraksi dengan sel kanker kolorektal.
## Metode
Langkah pertama kita mencari gen kanker kolorektal di website OMIM. Setelah mendapat datanya, kita ambil data approved symbolnya, lalu kita bersihkan dengan “Remove Duplicate”. Dengan bantuan literatur, kita mengambil senyawa-senyawa yang diduga dapat berinteraksi dengan gen kanker kolorektal. Pada studi ini kita mengambil senyawa dari jamur Chaga dan juga dari senyawa-senyawa lain.

Kita kemudian ke PubChem dan mengambil data SMILE dari senyawa-senyawa obat tersebut. Masukkan data SMILE ke Swiss Target Prediction dan ambil “common name” dari file-file Excel tersebut. Buat sheet excel sendiri untuk tiap-tiap senyawa dan hapus kolom yang tertulis N/A. Buat sheet excel sendiri yang merupakan gabungan dari keenam senyawa obat, jangan lupa hapus duplikat. Buat juga excel sendiri yang bertuliskan nama dan termasuk dalam senyawa apa target-target tersebut.

Buat di file excel baru satu sheet yang berisi semua senyawa penyakit dan juga semua senyawa obat yang bersebelahan. Kemudian buat irisan dari kedua data tersebut menggunakan website Venny, dan juga buat gabungan antara senyawa penyakit dan obat.

![Gambar Irisan](gambar_irisann.png)
![Tabel Irisan](tabel_irisan.png)

Masukkan hasil irisan dari data penyakit dan data obat ke website String untuk kemudian mendapat visualisasi protein-protein interaction irisan dari penyakit dan obat. Setelah irisan, buat gabungan dari senyawa penyakit dan obat dalam satu column, lalu masukkan ke String untuk mendapat visualisasi protein-protein interaction gabungan. Jadi sekarang kita mempunyai dua file, irisan dan gabungan dari senyawa penyakit dan obat.

![irisan string](irisan_string.png)*Irisan String*

Langkah berikutnya adalah visualisasi data menggunakan aplikasi Cytoscape. Masukkan file gabungan data dan kita dapat melihat data gabungan yang masif. Kemudian lakukan analyze network untuk melihat data-data dari senyawa gabungan tersebut seperti degree, betweenness centrality, dan closeness centrality.

![irisan cytoscape](irisan_cytoscape.png)*Irisan Cytoscape*

Kemudian aktifkan cytocluster dan gunakan untuk membuat cluster-cluster. Dalam studi ini terbentuk 13 cluster. Kita lalu membuat network dari cluster pertama. Network itu lalu kita analisis seperti biasa. Kita kemudian menghapus data-data analisis yang tidak kita butuhkan, dan sisakan degree, betweenness centrality, dan closeness centrality karena hanya data itu yang kita butuhkan.

Kita lalu ubah bentuk network menjadi lingkaran berdasarkan degree. Setelah disimpan, kita kembali ke main network. Dengan cytohubba kita ambil 20 data terpenting dari network tersebut. Rangking tertinggi pada network ini adalah EGFR. Kita kemudian membuka file irisan dan terdapat 9 nodes. Dengan Cytohubba didapatkan kalau node tertinggi adalah MTOR.

![tabel hub protein](tabel_hub_protein.png)*Tabel Hub Protein*

Kita kemudian melakukan enrichment analysis dengan ShinyGO. Top 20 senyawa yang kita dapatkan tadi kita masukkan ke dalam ShinyGO. Dari 20 senyawa tersebut yang menduduki posisi paling berpengaruh adalah “Prolactin Signaling Pathway”.

![enrichment analysis](enrichment_analysis.png)*Enrichment Analysis*

Kita lalu kembali ke String dan memasukkan 9 protein irisan yang tadi. Dari hasil analisis, kita akan mendownload biological process (gene ontology), molecular function (gene ontology), KEGG pathways, dan All Enriched Terms untuk kemudian divisualisasikan di Cytoscape. Kita buka file Enrichment KEGG dan mendapatkan 18 pathways.

Kita kemudian membuka file target-senyawa dan jangan lupa mengubah tanda di senyawa menjadi source node. Dan inilah network target-senyawa yang kita miliki. Kita juga membuka file string_interaction_irisan yang kita dapat di awal. Dan terakhir kita membuka file Enrichment KEGG yang berisi 18 pathways. Kita kemudian me-“merge” (menggabungkan) ketiga file tersebut dan inilah network yang kita miliki.

Kita kemudian pilih nodesnotes connected by selected edges. Selanjutnya kita memilih first neighborhood of selected nodes dan klik undirected. Kita lanjutkan dengan memilih new network dan from selected nodes, all edges. Dan inilah network pharmacology yang kita punya.
