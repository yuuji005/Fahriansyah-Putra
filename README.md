# Fahriansyah-Putra
class Koperasi:
    def __init__(self):
        self.anggota = {}

    def tambah_anggota("Fahri"):
        if nama not in self.anggota:("Anggota tidak terdaftar"):
            self.anggota[nama] = {
                "saldo": 10000,
                "simpanan": 10000,
                "pinjaman": 5000,
                "bunga": 50
            }
            print(f"Anggota {nama} berhasil ditambahkan.")
        else:
            print("Anggota sudah terdaftar.")

    def tambah_simpanan(self, nama, jumlah):
        if nama in self.anggota:
            self.anggota[nama]['simpanan'] += jumlah
            self.anggota[nama]['saldo'] += jumlah
            print(f"Simpanan {jumlah} berhasil ditambahkan untuk {nama}.")
        else:
            print("Anggota tidak terdaftar.")

    def ambil_pinjaman(self, nama, jumlah, durasi):
        if nama in self.anggota:
            if self.anggota[nama]['saldo'] >= jumlah * 0.5:  # Misal, pinjaman max 50% dari saldo
                bunga = self.hitung_bunga(jumlah, durasi)
                self.anggota[nama]['pinjaman'] += jumlah + bunga
                self.anggota[nama]['saldo'] += jumlah
                print(f"Pinjaman {jumlah} berhasil diambil oleh {nama}. Total pinjaman termasuk bunga: {self.anggota[nama]['pinjaman']}.")
            else:
                print("Saldo tidak mencukupi untuk mengambil pinjaman.")
        else:
            print("Anggota tidak terdaftar.")

    def bayar_cicilan(self, nama, jumlah):
        if nama in self.anggota:
            if jumlah <= self.anggota[nama]['pinjaman']:
                self.anggota[nama]['pinjaman'] -= jumlah
                self.anggota[nama]['saldo'] -= jumlah
                print(f"Cicilan {jumlah} berhasil dibayar oleh {nama}. Sisa pinjaman: {self.anggota[nama]['pinjaman']}.")
            else:
                print("Jumlah cicilan melebihi sisa pinjaman.")
        else:
            print("Anggota tidak terdaftar.")

    def hitung_bunga(self, jumlah, durasi):
        # Misal bunga 5% per bulan
        bunga = (jumlah * 0.05) * durasi
        return bunga

    def tampilkan_data(self, nama):
        if nama in self.anggota:
            print(f"Data Anggota {nama}: {self.anggota[nama]}")
        else:
            print("Anggota tidak terdaftar.")


# Contoh penggunaan
koperasi = Koperasi()
koperasi.tambah_anggota("Fahri")
koperasi.tambah_simpanan("Fahri", 10000)
koperasi.ambil_pinjaman("Fahri", 5000, 3)
koperasi.bayar_cicilan("Fahri", 2000)
koperasi.tampilkan_data("Fahri")
