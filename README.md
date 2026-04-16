# Tugas-python-menggunakan-list
Pendataan mahasiswa
mahasiswa = []

def tampilkan_data():
    if len(mahasiswa) == 0:
        print("\nData masih kosong!")
    else:
        print("\nDaftar Mahasiswa:")
        for i, mhs in enumerate(mahasiswa, start=1):
            print(f"{i}. Nama: {mhs['nama']}, Nilai: {mhs['nilai']}")

def tambah_data():
    nama = input("Masukkan nama mahasiswa: ")
    nilai = int(input("Masukkan nilai mahasiswa: "))
    data = {
        "nama": nama,
        "nilai": nilai
    }
    mahasiswa.append(data)
    print("Data berhasil ditambahkan!")

def hapus_data():
    tampilkan_data()
    if len(mahasiswa) > 0:
        index = int(input("Pilih nomor yang akan dihapus: ")) - 1
        if 0 <= index < len(mahasiswa):
            mahasiswa.pop(index)
            print("Data berhasil dihapus!")
        else:
            print("Index tidak valid!")

def cari_mahasiswa():
    keyword = input("Masukkan nama yang dicari: ").lower()
    ditemukan = False

    for mhs in mahasiswa:
        if keyword in mhs['nama'].lower():
            print(f"Ditemukan: {mhs['nama']} dengan nilai {mhs['nilai']}")
            ditemukan = True

    if not ditemukan:
        print("Data tidak ditemukan!")

def rata_rata_nilai():
    if len(mahasiswa) == 0:
        print("Belum ada data.")
    else:
        total = 0
        for mhs in mahasiswa:
            total += mhs['nilai']

        rata = total / len(mahasiswa)
        print(f"Rata-rata nilai: {rata:.2f}")

# Program utama (while loop)
while True:
    print("\n=== MENU ===")
    print("1. Tampilkan Data")
    print("2. Tambah Data")
    print("3. Hapus Data")
    print("4. Cari Mahasiswa")
    print("5. Hitung Rata-rata Nilai")
    print("6. Keluar")

    pilihan = input("Pilih menu (1-6): ")

    if pilihan == "1":
        tampilkan_data()
    elif pilihan == "2":
        tambah_data()
    elif pilihan == "3":
        hapus_data()
    elif pilihan == "4":
        cari_mahasiswa()
    elif pilihan == "5":
        rata_rata_nilai()
    elif pilihan == "6":
        print("Program selesai.")
        break
    else:
        print("Pilihan tidak valid!")
