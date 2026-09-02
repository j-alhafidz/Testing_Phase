# Test Case - Fitur Produk
## Distribution Center (Hub) - Koperasi Desa Merah Putih

**Role**: Admin Perencanaan  
**Fitur**: Produk  
**Tipe Testing**: Functional Testing & UI/UX Testing  
**Tanggal**: 2 September 2026

---

## 1. FUNCTIONAL TESTING

### 1.1 Tampilan Halaman Produk

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-PROD-001 | Verifikasi tampilan halaman list produk | User sudah login sebagai Admin Perencanaan | 1. Login ke sistem<br>2. Klik menu "Produk" di sidebar | 1. Halaman produk ditampilkan dengan benar<br>2. Terdapat tabel dengan kolom: No, Thumbnail, Nama produk, Katalog, Tipe, Satuan, Aksi<br>3. Terdapat search bar "Cari nama produk atau nomor SKU..."<br>4. Terdapat tombol "+ Tambah produk"<br>5. Terdapat tabs: Produk, Inventaris, Supplier<br>6. Terdapat pagination di bagian bawah |
| TC-PROD-002 | Verifikasi jumlah data yang ditampilkan | User berada di halaman Produk | 1. Lihat tabel produk<br>2. Hitung jumlah baris data<br>3. Lihat informasi "Total X Data" | Jumlah data yang ditampilkan sesuai dengan total data yang tertera di pagination |
| TC-PROD-003 | Verifikasi thumbnail produk | Terdapat produk dengan foto | 1. Lihat kolom Thumbnail<br>2. Periksa gambar produk | Thumbnail produk ditampilkan dengan jelas dan proporsional (tidak pecah/blur) |
| TC-PROD-004 | Verifikasi label tipe produk | Terdapat produk dengan tipe Subsidi dan Non Subsidi | 1. Lihat kolom Tipe<br>2. Periksa label Subsidi dan Non Subsidi | 1. Label "Subsidi" berwarna biru<br>2. Label "Non Subsidi" berwarna abu-abu/netral<br>3. Label mudah dibedakan secara visual |

### 1.2 Fungsi Search/Pencarian

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-PROD-005 | Search produk dengan nama lengkap | User berada di halaman Produk dengan minimal 5 data produk | 1. Klik search bar<br>2. Ketik "Aqua 330ml"<br>3. Tekan Enter atau tunggu auto-search | Sistem menampilkan produk "Aqua 330ml" saja |
| TC-PROD-006 | Search produk dengan nama sebagian | User berada di halaman Produk | 1. Klik search bar<br>2. Ketik "GAS"<br>3. Tekan Enter atau tunggu auto-search | Sistem menampilkan semua produk yang mengandung kata "GAS" (contoh: GAS LPG 12 KG) |
| TC-PROD-007 | Search produk dengan huruf kecil | User berada di halaman Produk | 1. Klik search bar<br>2. Ketik "aqua" (huruf kecil)<br>3. Tekan Enter atau tunggu auto-search | Sistem menampilkan produk "Aqua 330ml" (search case-insensitive) |
| TC-PROD-008 | Search produk dengan SKU | User berada di halaman Produk, produk memiliki nomor SKU | 1. Klik search bar<br>2. Ketik nomor SKU produk (contoh: "SKU001")<br>3. Tekan Enter | Sistem menampilkan produk dengan SKU yang sesuai |
| TC-PROD-009 | Search produk yang tidak ada | User berada di halaman Produk | 1. Klik search bar<br>2. Ketik "ZZZZZZ" (produk yang tidak ada)<br>3. Tekan Enter | 1. Tabel menampilkan pesan "Data tidak ditemukan" atau empty state<br>2. Tidak ada error yang muncul |
| TC-PROD-010 | Clear search | User sudah melakukan pencarian | 1. Hapus teks di search bar<br>2. Tekan Enter atau tunggu auto-search | Sistem menampilkan kembali semua data produk |

### 1.3 Fungsi Tambah Produk

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-PROD-011 | Membuka modal Tambah Produk | User berada di halaman Produk | 1. Klik tombol "+ Tambah produk" | 1. Modal "Tambah Produk" muncul<br>2. Modal memiliki overlay gelap di background<br>3. Terdapat form dengan field: Katalog, Nama produk*, Satuan*, Tipe*, Foto produk<br>4. Terdapat tombol "Batal" dan "Simpan"<br>5. Terdapat tombol close (X) di pojok kanan atas |
| TC-PROD-012 | Validasi field required | Modal Tambah Produk terbuka | 1. Jangan isi field apapun<br>2. Klik tombol "Simpan" | 1. Muncul pesan error untuk field required (Nama produk, Satuan, Tipe)<br>2. Data tidak tersimpan<br>3. Modal masih terbuka |
| TC-PROD-013 | Tambah produk dengan data valid - tanpa katalog | Modal Tambah Produk terbuka | 1. Kosongkan field Katalog<br>2. Isi Nama produk: "Indomie Goreng"<br>3. Pilih Satuan: "Pcs"<br>4. Pilih Tipe: "Non Subsidi"<br>5. Klik "Simpan" | 1. Modal tertutup<br>2. Produk baru muncul di tabel<br>3. Muncul notifikasi sukses<br>4. Data produk tersimpan dengan field Katalog kosong |
| TC-PROD-014 | Tambah produk dengan data lengkap | Modal Tambah Produk terbuka, terdapat katalog di database | 1. Pilih Katalog dari dropdown<br>2. Isi Nama produk: "Aqua Galon 19L"<br>3. Pilih Satuan: "Galon"<br>4. Pilih Tipe: "Non Subsidi"<br>5. Upload foto produk (JPG, < 10MB)<br>6. Klik "Simpan" | 1. Modal tertutup<br>2. Produk baru muncul di tabel dengan thumbnail<br>3. Muncul notifikasi sukses "Produk berhasil ditambahkan" atau sejenisnya<br>4. Data tersimpan dengan benar di semua kolom |
| TC-PROD-015 | Upload foto produk format JPG | Modal Tambah Produk terbuka | 1. Isi semua field required<br>2. Klik area upload foto atau drag file JPG (< 10MB)<br>3. Klik "Simpan" | 1. File berhasil di-upload<br>2. Muncul preview thumbnail<br>3. Produk tersimpan dengan foto |
| TC-PROD-016 | Upload foto produk format PNG | Modal Tambah Produk terbuka | 1. Isi semua field required<br>2. Upload file PNG (< 10MB)<br>3. Klik "Simpan" | 1. File berhasil di-upload<br>2. Produk tersimpan dengan foto |
| TC-PROD-017 | Upload foto produk format JPEG | Modal Tambah Produk terbuka | 1. Isi semua field required<br>2. Upload file JPEG (< 10MB)<br>3. Klik "Simpan" | 1. File berhasil di-upload<br>2. Produk tersimpan dengan foto |
| TC-PROD-018 | Upload foto produk ukuran > 10MB | Modal Tambah Produk terbuka | 1. Isi semua field required<br>2. Upload file gambar > 10MB<br>3. Klik "Simpan" | 1. Muncul pesan error "Ukuran file maksimal 10MB"<br>2. File tidak terupload<br>3. User bisa upload file lain |
| TC-PROD-019 | Upload foto produk format tidak valid | Modal Tambah Produk terbuka | 1. Isi semua field required<br>2. Upload file selain JPG/JPEG/PNG (contoh: .pdf, .gif, .webp)<br>3. Klik "Simpan" | 1. Muncul pesan error "Format file harus JPG/JPEG/PNG"<br>2. File tidak terupload |
| TC-PROD-020 | Tambah produk dengan nama yang sudah ada | Modal Tambah Produk terbuka, sudah ada produk "Aqua 330ml" | 1. Isi Nama produk: "Aqua 330ml"<br>2. Isi field lain dengan valid<br>3. Klik "Simpan" | 1. Muncul pesan error "Nama produk sudah ada" atau sistem membiarkan duplikat (tergantung business rule)<br>2. Konsistensi harus dijaga |
| TC-PROD-021 | Cancel tambah produk | Modal Tambah Produk terbuka, user sudah mengisi beberapa field | 1. Isi beberapa field<br>2. Klik tombol "Batal" | 1. Modal tertutup<br>2. Data tidak tersimpan<br>3. Kembali ke halaman list produk |
| TC-PROD-022 | Close modal dengan tombol X | Modal Tambah Produk terbuka, user sudah mengisi beberapa field | 1. Isi beberapa field<br>2. Klik tombol X di pojok kanan atas | 1. Modal tertutup<br>2. Data tidak tersimpan<br>3. Kembali ke halaman list produk |
| TC-PROD-023 | Close modal dengan klik overlay | Modal Tambah Produk terbuka | 1. Klik area gelap di luar modal (overlay) | 1. Modal tertutup atau tetap terbuka (tergantung UX design)<br>2. Konsisten dengan behavior modal lain di sistem |

### 1.4 Fungsi Edit Produk

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-PROD-024 | Membuka modal Edit Produk | User berada di halaman Produk dengan minimal 1 data produk | 1. Klik icon edit (pensil kuning) pada salah satu produk | 1. Modal "Ubah Produk" muncul<br>2. Form sudah terisi dengan data produk yang dipilih<br>3. Field yang ada: Katalog, Nama produk*, Satuan*, Tipe*, Foto produk<br>4. Terdapat tombol "Batal" dan "Simpan" |
| TC-PROD-025 | Edit nama produk | Modal Ubah Produk terbuka dengan data "Aqua 330ml" | 1. Ubah Nama produk menjadi "Aqua 330ml Premium"<br>2. Klik "Simpan" | 1. Modal tertutup<br>2. Data produk di tabel ter-update menjadi "Aqua 330ml Premium"<br>3. Muncul notifikasi sukses |
| TC-PROD-026 | Edit satuan produk | Modal Ubah Produk terbuka | 1. Ubah Satuan dari "Botol" ke "Pcs"<br>2. Klik "Simpan" | 1. Modal tertutup<br>2. Satuan produk ter-update di tabel<br>3. Muncul notifikasi sukses |
| TC-PROD-027 | Edit tipe produk | Modal Ubah Produk terbuka dengan produk "Non Subsidi" | 1. Ubah Tipe dari "Non Subsidi" ke "Subsidi"<br>2. Klik "Simpan" | 1. Modal tertutup<br>2. Label tipe berubah dari abu-abu ke biru di tabel<br>3. Muncul notifikasi sukses |
| TC-PROD-028 | Edit katalog produk | Modal Ubah Produk terbuka | 1. Pilih katalog berbeda dari dropdown<br>2. Klik "Simpan" | 1. Modal tertutup<br>2. Katalog produk ter-update di tabel<br>3. Muncul notifikasi sukses |
| TC-PROD-029 | Edit foto produk | Modal Ubah Produk terbuka dengan produk yang sudah punya foto | 1. Hapus atau ganti foto produk dengan foto baru<br>2. Klik "Simpan" | 1. Modal tertutup<br>2. Thumbnail produk ter-update di tabel<br>3. Muncul notifikasi sukses |
| TC-PROD-030 | Edit produk - kosongkan field required | Modal Ubah Produk terbuka | 1. Hapus isi field Nama produk (kosongkan)<br>2. Klik "Simpan" | 1. Muncul pesan error "Nama produk wajib diisi"<br>2. Data tidak tersimpan<br>3. Modal masih terbuka |
| TC-PROD-031 | Cancel edit produk | Modal Ubah Produk terbuka, user sudah mengubah beberapa field | 1. Ubah beberapa field<br>2. Klik tombol "Batal" | 1. Modal tertutup<br>2. Perubahan tidak tersimpan<br>3. Data produk tetap seperti sebelumnya |
| TC-PROD-032 | Edit produk tanpa perubahan | Modal Ubah Produk terbuka | 1. Jangan ubah field apapun<br>2. Klik "Simpan" | 1. Modal tertutup<br>2. Tidak ada perubahan data<br>3. Muncul notifikasi sukses atau tidak ada notifikasi (tergantung design) |

### 1.5 Fungsi Hapus Produk

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-PROD-033 | Membuka modal konfirmasi hapus | User berada di halaman Produk dengan minimal 1 data produk | 1. Klik icon delete (tong sampah merah) pada salah satu produk | 1. Modal "Hapus Produk" muncul<br>2. Terdapat icon tong sampah merah di atas<br>3. Terdapat pesan: "Apakah Anda yakin ingin menghapus [Nama Produk]? Tindakan ini tidak dapat dibatalkan."<br>4. Terdapat tombol "Batal" dan "Hapus" (merah) |
| TC-PROD-034 | Konfirmasi hapus produk | Modal Hapus Produk terbuka untuk produk "Aqua 330ml" | 1. Klik tombol "Hapus" | 1. Modal tertutup<br>2. Produk "Aqua 330ml" hilang dari tabel<br>3. Total data berkurang 1<br>4. Muncul notifikasi sukses "Produk berhasil dihapus" |
| TC-PROD-035 | Cancel hapus produk | Modal Hapus Produk terbuka | 1. Klik tombol "Batal" | 1. Modal tertutup<br>2. Produk tidak dihapus<br>3. Data tetap ada di tabel |
| TC-PROD-036 | Close modal hapus dengan tombol X | Modal Hapus Produk terbuka | 1. Klik tombol X di pojok kanan atas | 1. Modal tertutup<br>2. Produk tidak dihapus<br>3. Data tetap ada di tabel |
| TC-PROD-037 | Hapus produk yang sedang digunakan di transaksi | User akan hapus produk yang masih ada di pesanan/rencana belanja | 1. Pilih produk yang sedang digunakan<br>2. Klik icon delete<br>3. Klik "Hapus" | 1. Muncul pesan error "Produk tidak dapat dihapus karena masih digunakan" atau sejenisnya<br>2. Produk tidak terhapus<br>ATAU sistem membiarkan hapus (soft delete) tergantung business rule |

### 1.6 Fungsi Pagination

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-PROD-038 | Verifikasi pagination dengan data < 10 | Database memiliki 5 produk | 1. Buka halaman Produk<br>2. Lihat pagination | 1. Semua 5 produk ditampilkan dalam 1 halaman<br>2. Terdapat info "Total 5 Data"<br>3. Halaman aktif adalah halaman 1 |
| TC-PROD-039 | Pagination dengan data > 10 | Database memiliki 15 produk, setting 10/page | 1. Buka halaman Produk<br>2. Lihat pagination | 1. Halaman 1 menampilkan 10 produk<br>2. Terdapat tombol next (>) aktif<br>3. Info "Total 15 Data" |
| TC-PROD-040 | Navigasi ke halaman berikutnya | Terdapat minimal 11 produk, user di halaman 1 | 1. Klik tombol next (>) | 1. Pindah ke halaman 2<br>2. Menampilkan produk ke-11 dst<br>3. Tombol prev (<) menjadi aktif<br>4. URL atau indicator halaman berubah ke 2 |
| TC-PROD-041 | Navigasi ke halaman sebelumnya | User berada di halaman 2 atau lebih | 1. Klik tombol prev (<) | 1. Kembali ke halaman sebelumnya<br>2. Data halaman sebelumnya ditampilkan |
| TC-PROD-042 | Ubah jumlah data per halaman | Terdapat minimal 15 produk | 1. Klik dropdown "10 / page"<br>2. Pilih opsi lain (misal 20, 50, 100) | 1. Jumlah data yang ditampilkan berubah sesuai pilihan<br>2. Pagination menyesuaikan jumlah halaman |
| TC-PROD-043 | Pagination setelah tambah produk | User di halaman terakhir dengan data pas batas | 1. Tambah 1 produk baru<br>2. Lihat pagination | 1. Total data bertambah 1<br>2. Produk baru muncul di posisi yang tepat (atas/bawah tergantung sorting)<br>3. Pagination update jika perlu halaman baru |

### 1.7 Fungsi Navigasi Tab

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-PROD-044 | Klik tab Inventaris | User berada di tab Produk | 1. Klik tab "Inventaris" | 1. Berpindah ke halaman/tab Inventaris<br>2. Tab Inventaris menjadi aktif (highlight)<br>3. Konten berubah sesuai fungsi Inventaris |
| TC-PROD-045 | Klik tab Supplier | User berada di tab Produk | 1. Klik tab "Supplier" | 1. Berpindah ke halaman/tab Supplier<br>2. Tab Supplier menjadi aktif<br>3. Konten berubah sesuai fungsi Supplier |
| TC-PROD-046 | Kembali ke tab Produk | User berada di tab lain (Inventaris/Supplier) | 1. Klik tab "Produk" | 1. Kembali ke halaman Produk<br>2. Tab Produk menjadi aktif<br>3. Data produk ditampilkan kembali |

---

## 2. UI/UX TESTING

### 2.1 Responsiveness

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-UI-001 | Tampilan di Desktop (1920x1080) | Buka halaman Produk di browser desktop | 1. Buka halaman di resolusi 1920x1080<br>2. Periksa layout | 1. Semua elemen terlihat dengan baik<br>2. Tidak ada overlap<br>3. Whitespace proporsional<br>4. Tabel tidak terpotong |
| TC-UI-002 | Tampilan di Laptop (1366x768) | Buka halaman Produk di resolusi laptop standar | 1. Resize browser ke 1366x768<br>2. Periksa layout | 1. Layout responsive dan mudah dibaca<br>2. Tidak ada horizontal scroll berlebihan<br>3. Modal masih center dan proporsional |
| TC-UI-003 | Tampilan di Tablet (768x1024) | Buka halaman di tablet atau resize browser | 1. Akses dari tablet atau resize ke 768px<br>2. Periksa semua elemen | 1. Sidebar collapse atau responsive<br>2. Tabel adjust dengan baik<br>3. Tombol dan form tetap usable<br>4. Modal fit di layar |
| TC-UI-004 | Tampilan di Mobile (375x667) | Buka halaman di smartphone atau resize browser | 1. Akses dari mobile atau resize ke 375px<br>2. Test semua fungsi | 1. Layout stack secara vertikal<br>2. Tabel scrollable horizontal atau reformat<br>3. Modal penuh layar atau optimized<br>4. Tombol mudah di-tap (min 44x44px) |

### 2.2 Visual Design & Consistency

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-UI-005 | Konsistensi warna tombol | Periksa semua tombol di halaman Produk | 1. Lihat warna tombol "Tambah produk"<br>2. Lihat warna tombol "Simpan"<br>3. Lihat warna tombol "Hapus" | 1. Tombol primary (Tambah, Simpan) konsisten warna teal<br>2. Tombol destructive (Hapus) konsisten warna merah<br>3. Tombol secondary (Batal) konsisten warna netral |
| TC-UI-006 | Konsistensi font | Periksa typography di seluruh halaman | 1. Periksa font family<br>2. Periksa font size untuk header, body, label<br>3. Periksa line height dan letter spacing | 1. Font konsisten di seluruh aplikasi<br>2. Hierarchy jelas (H1 > H2 > Body)<br>3. Mudah dibaca |
| TC-UI-007 | Konsistensi icon | Periksa semua icon di halaman | 1. Lihat icon edit (pensil)<br>2. Lihat icon delete (trash)<br>3. Lihat icon di form | 1. Icon style konsisten (outline/filled)<br>2. Icon size proporsional<br>3. Icon color sesuai fungsi |
| TC-UI-008 | Spacing dan alignment | Periksa jarak antar elemen | 1. Periksa padding/margin card<br>2. Periksa spacing form field<br>3. Periksa alignment tabel | 1. Spacing konsisten dan proporsional<br>2. Elemen aligned dengan baik<br>3. Tidak ada elemen yang bersentuhan |
| TC-UI-009 | Contrast dan accessibility | Periksa kontras warna teks dan background | 1. Test contrast ratio text dan background<br>2. Test visibility label Subsidi/Non Subsidi | 1. Contrast ratio minimal 4.5:1 (WCAG AA)<br>2. Semua teks mudah dibaca<br>3. Label jelas dibedakan |

### 2.3 Interaktivitas

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-UI-010 | Hover effect tombol | User hover mouse di atas tombol | 1. Hover tombol "Tambah produk"<br>2. Hover tombol "Simpan"<br>3. Hover icon edit/delete | 1. Tombol berubah warna/opacity saat hover<br>2. Cursor berubah jadi pointer<br>3. Feedback visual jelas |
| TC-UI-011 | Focus state input field | User klik atau tab ke input field | 1. Klik field Nama produk<br>2. Tab ke field lain | 1. Field yang active memiliki border highlight<br>2. Outline visible untuk keyboard navigation<br>3. Placeholder text berubah/hilang dengan smooth |
| TC-UI-012 | Loading state | Trigger aksi yang membutuhkan waktu (save, delete) | 1. Klik "Simpan" saat tambah produk<br>2. Tunggu response | 1. Muncul loading indicator (spinner/skeleton)<br>2. Tombol disabled saat loading<br>3. User tidak bisa submit ganda |
| TC-UI-013 | Disabled state | Periksa tombol/field dalam kondisi disabled | 1. Submit form tanpa isi field required<br>2. Lihat tombol prev di halaman 1 | 1. Elemen disabled memiliki opacity lebih rendah<br>2. Cursor menunjukkan not-allowed<br>3. Tidak bisa di-interact |

### 2.4 Feedback & Notification

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-UI-014 | Notifikasi sukses tambah produk | User berhasil tambah produk | 1. Tambah produk dengan data valid<br>2. Klik Simpan<br>3. Lihat notifikasi | 1. Muncul toast/alert sukses (warna hijau)<br>2. Pesan jelas: "Produk berhasil ditambahkan"<br>3. Notifikasi auto-hide setelah 3-5 detik |
| TC-UI-015 | Notifikasi error validasi | User submit form tanpa isi field required | 1. Buka modal Tambah Produk<br>2. Langsung klik Simpan<br>3. Lihat error message | 1. Error message muncul di bawah/dekat field yang error<br>2. Field error di-highlight dengan border merah<br>3. Pesan error spesifik dan membantu |
| TC-UI-016 | Notifikasi sukses edit produk | User berhasil edit produk | 1. Edit produk<br>2. Klik Simpan<br>3. Lihat notifikasi | 1. Muncul notifikasi sukses<br>2. Pesan: "Produk berhasil diperbarui" atau sejenisnya<br>3. Auto-hide setelah 3-5 detik |
| TC-UI-017 | Notifikasi sukses hapus produk | User berhasil hapus produk | 1. Hapus produk<br>2. Konfirmasi hapus<br>3. Lihat notifikasi | 1. Muncul notifikasi sukses (hijau)<br>2. Pesan: "Produk berhasil dihapus"<br>3. Auto-hide setelah 3-5 detik |
| TC-UI-018 | Notifikasi error sistem | Trigger error (misal: koneksi terputus) | 1. Matikan koneksi internet<br>2. Coba submit form<br>3. Lihat error | 1. Muncul notifikasi error (merah)<br>2. Pesan error informatif<br>3. Ada guidance untuk retry/next action |

### 2.5 User Experience Flow

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-UX-001 | Kecepatan load halaman | User membuka halaman Produk | 1. Clear cache<br>2. Buka halaman Produk<br>3. Ukur waktu load | 1. Halaman load dalam < 3 detik<br>2. Skeleton/loading state muncul saat load<br>3. Progressive loading untuk gambar |
| TC-UX-002 | Smooth modal animation | User membuka modal | 1. Klik "Tambah produk"<br>2. Lihat animasi modal<br>3. Close modal | 1. Modal muncul dengan animasi smooth (fade/slide)<br>2. Tidak ada janking<br>3. Close animation smooth |
| TC-UX-003 | Keyboard navigation | User navigasi dengan keyboard | 1. Tab dari field ke field di form<br>2. Tekan Enter di search<br>3. Tekan Esc di modal | 1. Tab order logis dan mengikuti visual flow<br>2. Enter submit form/search<br>3. Esc menutup modal<br>4. Semua interactive element reachable via keyboard |
| TC-UX-004 | Undo/konfirmasi aksi destructive | User akan hapus produk | 1. Klik icon delete<br>2. Lihat modal konfirmasi | 1. Modal konfirmasi muncul dengan pesan warning<br>2. Jelas menyebutkan nama produk<br>3. Tombol Hapus berwarna merah (destructive)<br>4. Ada opsi Batal yang mudah diakses |
| TC-UX-005 | Empty state | Database tidak memiliki produk atau hasil search kosong | 1. Hapus semua produk atau search yang tidak ada<br>2. Lihat tampilan tabel | 1. Muncul ilustrasi/icon empty state<br>2. Pesan informatif: "Belum ada produk" atau "Data tidak ditemukan"<br>3. Ada CTA untuk tambah produk (jika applicable) |
| TC-UX-006 | Form validation real-time | User mengisi form | 1. Buka modal Tambah Produk<br>2. Mulai ketik di field Nama produk<br>3. Kosongkan field | 1. Validasi muncul setelah user blur dari field atau saat submit<br>2. Tidak mengganggu saat user sedang mengetik<br>3. Error message hilang saat field sudah valid |
| TC-UX-007 | Placeholder dan label yang jelas | User membuka form | 1. Buka modal Tambah Produk<br>2. Lihat semua field | 1. Setiap field punya label yang jelas<br>2. Placeholder memberikan contoh/hint<br>3. Field required ditandai dengan (*)<br>4. Instruction untuk upload file jelas |
| TC-UX-008 | Drag and drop file upload | User upload foto produk | 1. Buka modal Tambah Produk<br>2. Drag file gambar ke area upload<br>3. Drop file | 1. Area upload highlight saat drag over<br>2. File langsung ter-upload setelah drop<br>3. Muncul preview thumbnail<br>4. Ada opsi remove/ganti |
| TC-UX-009 | Data persistence setelah error | User submit form dan dapat error | 1. Isi form lengkap<br>2. Upload foto > 10MB (trigger error)<br>3. Lihat kondisi form | 1. Data yang sudah diisi tidak hilang<br>2. User hanya perlu fix error (ganti foto)<br>3. Tidak perlu mengisi ulang semua field |
| TC-UX-010 | Breadcrumb atau navigation clarity | User berada di halaman Produk | 1. Lihat sidebar dan header<br>2. Cek indicator halaman aktif | 1. Menu "Produk" di sidebar ter-highlight<br>2. Tab "Produk" ter-highlight<br>3. User tahu posisi mereka di aplikasi |

### 2.6 Accessibility

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-ACC-001 | Screen reader compatibility | User dengan screen reader mengakses halaman | 1. Aktifkan screen reader (NVDA/JAWS)<br>2. Navigate halaman Produk | 1. Semua elemen ter-announce dengan benar<br>2. Alt text untuk gambar/icon ada<br>3. Form label ter-associate dengan input |
| TC-ACC-002 | Keyboard-only navigation | User hanya menggunakan keyboard | 1. Navigasi seluruh halaman dengan Tab/Shift+Tab<br>2. Akses modal, form, dan aksi dengan keyboard | 1. Semua fungsi accessible via keyboard<br>2. Focus indicator visible<br>3. Tidak ada keyboard trap |
| TC-ACC-003 | Color contrast | Periksa dengan contrast checker | 1. Test contrast ratio semua text<br>2. Test contrast label Subsidi/Non Subsidi | 1. Semua text memenuhi WCAG AA (4.5:1)<br>2. Large text memenuhi 3:1<br>3. Interactive element jelas tanpa mengandalkan warna saja |
| TC-ACC-004 | Error announcement | User dengan screen reader submit form error | 1. Aktifkan screen reader<br>2. Submit form kosong<br>3. Dengar announcement | 1. Error ter-announce oleh screen reader<br>2. User diberi tahu field mana yang error<br>3. Focus pindah ke field pertama yang error |

---

## 3. EDGE CASES & SPECIAL SCENARIOS

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-EDGE-001 | Produk dengan nama sangat panjang | User tambah produk dengan nama 200+ karakter | 1. Isi Nama produk dengan teks sangat panjang<br>2. Simpan | 1. Sistem handle dengan baik (truncate/wrap)<br>2. Tabel tidak rusak layout<br>3. Tooltip untuk lihat nama lengkap (jika di-truncate) |
| TC-EDGE-002 | Produk tanpa thumbnail | Produk tidak memiliki foto | 1. Tambah produk tanpa upload foto<br>2. Lihat di tabel | 1. Muncul placeholder image default<br>2. Tetap terlihat rapi dan konsisten |
| TC-EDGE-003 | Multiple user concurrent edit | 2 user edit produk yang sama bersamaan | 1. User A buka edit produk X<br>2. User B juga buka edit produk X<br>3. User A simpan perubahan<br>4. User B simpan perubahan | 1. Sistem handle conflict (last write win / optimistic locking)<br>2. Ada warning jika data berubah<br>3. Tidak ada data corruption |
| TC-EDGE-004 | Session timeout saat mengisi form | User mengisi form tapi session timeout | 1. Buka modal Tambah Produk<br>2. Isi form lengkap<br>3. Tunggu sampai session timeout<br>4. Klik Simpan | 1. Muncul pesan session expired<br>2. User redirect ke login<br>3. Idealnya: form data preserved setelah re-login |
| TC-EDGE-005 | Browser back button | User buka modal lalu klik back di browser | 1. Buka modal Tambah Produk<br>2. Klik browser back button | 1. Modal tertutup ATAU<br>2. Kembali ke halaman sebelumnya (tergantung routing implementation)<br>3. Behaviour konsisten dan tidak error |
| TC-EDGE-006 | Rapid clicking | User klik tombol save berkali-kali dengan cepat | 1. Isi form dengan valid<br>2. Klik tombol "Simpan" 5x dengan cepat | 1. Tombol disabled setelah first click<br>2. Data hanya tersimpan 1x<br>3. Tidak ada duplicate entry |
| TC-EDGE-007 | Special characters di nama produk | User input special char di nama | 1. Isi Nama produk: "Aqua™ 330ml (Premium) - @2026!"<br>2. Simpan | 1. Sistem accept atau sanitize dengan benar<br>2. Tidak ada SQL injection vulnerability<br>3. Tidak ada XSS vulnerability<br>4. Display dengan benar di tabel |
| TC-EDGE-008 | Network interruption saat upload | Koneksi terputus saat upload foto | 1. Mulai upload foto besar<br>2. Putus koneksi saat upload<br>3. Klik Simpan | 1. Muncul error message jelas<br>2. User bisa retry<br>3. Tidak ada partial/corrupted data |
| TC-EDGE-009 | Database dengan 10,000+ produk | Sistem memiliki ribuan produk | 1. Access halaman dengan data besar<br>2. Test pagination<br>3. Test search | 1. Performance tetap baik (< 3s load)<br>2. Pagination efficient (server-side)<br>3. Search responsive |
| TC-EDGE-010 | XSS attempt via product name | User coba inject script | 1. Isi Nama produk: `<script>alert('XSS')</script>`<br>2. Simpan<br>3. View di tabel | 1. Script tidak ter-execute<br>2. Escaped/sanitized dengan benar<br>3. Display aman |

---

## 4. COMPATIBILITY TESTING

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-COMP-001 | Chrome browser (latest) | Akses dari Chrome | 1. Buka aplikasi di Chrome latest<br>2. Test semua fitur Produk | Semua fungsi bekerja dengan baik tanpa error |
| TC-COMP-002 | Firefox browser (latest) | Akses dari Firefox | 1. Buka aplikasi di Firefox latest<br>2. Test semua fitur Produk | Semua fungsi bekerja dengan baik tanpa error |
| TC-COMP-003 | Safari browser (macOS) | Akses dari Safari | 1. Buka aplikasi di Safari<br>2. Test semua fitur Produk | Semua fungsi bekerja dengan baik tanpa error |
| TC-COMP-004 | Edge browser (latest) | Akses dari Edge | 1. Buka aplikasi di Edge latest<br>2. Test semua fitur Produk | Semua fungsi bekerja dengan baik tanpa error |
| TC-COMP-005 | Mobile Safari (iOS) | Akses dari iPhone/iPad | 1. Buka aplikasi di Safari iOS<br>2. Test semua fitur | Layout responsive, fungsi bekerja, touch interaction smooth |
| TC-COMP-006 | Chrome Mobile (Android) | Akses dari Android | 1. Buka aplikasi di Chrome Android<br>2. Test semua fitur | Layout responsive, fungsi bekerja, touch interaction smooth |

---

## 5. PERFORMANCE TESTING

| Use Test Case | Test Scenario/Description | Pre-Condition | Test Case/Test Data | Expected Result |
|--------------|---------------------------|---------------|---------------------|-----------------|
| TC-PERF-001 | Page load time | Buka halaman Produk dengan fresh cache | 1. Clear cache<br>2. Load halaman<br>3. Measure time | Page load < 3 detik (ideal < 2 detik) |
| TC-PERF-002 | Search response time | User search produk | 1. Ketik di search bar<br>2. Measure response time | Result muncul dalam < 1 detik |
| TC-PERF-003 | Form submission time | User submit form tambah produk | 1. Isi form valid<br>2. Klik Simpan<br>3. Measure time sampai success | Proses selesai dalam < 2 detik |
| TC-PERF-004 | Image upload time | Upload foto produk | 1. Upload gambar 5MB<br>2. Measure upload time | Upload selesai dalam < 5 detik (tergantung koneksi) |
| TC-PERF-005 | Pagination performance | Navigate antar halaman | 1. Klik next/prev pagination<br>2. Measure load time | Data muncul dalam < 1 detik |

---

## SUMMARY & NOTES

**Total Test Cases**: 88 test cases
- Functional Testing: 46 test cases
- UI/UX Testing: 32 test cases  
- Edge Cases: 10 test cases
- Compatibility Testing: 6 test cases
- Performance Testing: 5 test cases

**Priority Levels** (recommended):
- **P0 (Critical)**: TC-PROD-001, TC-PROD-011, TC-PROD-014, TC-PROD-024, TC-PROD-033, TC-PROD-034
- **P1 (High)**: Semua test case CRUD utama, validasi, dan security
- **P2 (Medium)**: UI/UX testing, responsive, feedback
- **P3 (Low)**: Edge cases, compatibility di browser jarang

**Test Environment**:
- Browser: Chrome, Firefox, Safari, Edge (latest versions)
- Devices: Desktop (1920x1080), Laptop (1366x768), Tablet (768x1024), Mobile (375x667)
- Network: Fast 3G, 4G, WiFi
- OS: Windows 10/11, macOS, iOS, Android

**Test Data Requirements**:
- Minimal 15 produk dummy untuk testing pagination
- Gambar test dalam format JPG, PNG, JPEG dengan berbagai ukuran (< 10MB dan > 10MB)
- Katalog dummy minimal 3 jenis
- User test: Admin Perencanaan dengan permission penuh

**Known Issues/Observations** (to be filled during testing):
- [Issue #1]: ...
- [Issue #2]: ...

**Sign Off**:
- Tester: _________________
- Date: _________________
- Status: [ ] Pass [ ] Fail [ ] Conditional Pass
