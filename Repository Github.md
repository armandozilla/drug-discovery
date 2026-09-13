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
*	Di SwissDock persiapkan ligan (Ergosterol Peroxide), 4JSX sebagai protein target, posisi ligan di protein yang sudah didapatkan di PrankWeb
*	Mulai lakukan Docking


