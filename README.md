# PRAKTIKUM 6

Nama : Dhea Dwi Adelia

NIM : 312210116

Kelas : TI.22.A.1

### Latihan
Ubahlah kode dibawah ini menjadi fungsi menggunakan lambda

    import math

    def a(x):
    return x**2

    def b(x, y):
    return math.sqrt(x**2 + y**2)

    def c(*args):
    return sum(args)/len(args)

    def d(s):
    return "".join(set(s))

#### Script
    import math
    # Dhea Dwi Adelia

    def a(n): return lambda x: x**n

    lambdaA=a(4)
    print(lambdaA(4))

    def b(i,j):
        return lambda x, y: math.sqrt(x**i + y**j)

    lambdaB=b(4,0)
    print(lambdaB(3,0))

    def c(*args):
        return lambda *params:sum(args)/len(params)

    lambdaC=c(1, 2, 3, 4, 5)
    print(lambdaC(2, 2, 5))

    def d(firstname):
        return lambda *lastname: "".join(set(firstname)) + "".join(set(lastname))

    lambdaD=d("Dhea")
    print(lambdaD("Dwi", "Adelia"))
    
 ![Screenshot (160)](https://user-images.githubusercontent.com/115794875/205831450-d408cc5f-eae4-49bf-877d-e463c52ac1b7.png)
    
#### Berikut hasil run

 ![Screenshot (162)](https://user-images.githubusercontent.com/115794875/205831745-89f1a1bc-647a-4b58-ba0f-dbb3964efd98.png)

### Praktikum

Buat program sederhana dengan mengaplikasikan penggunaan fungsi yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan :

- Fungsi tambah() untuk menambah data.
- Fungsi tampilkan() untuk menampilkan data.
- Fungsi hapus(nama) untuk menghapus data berdasarkan nama.
- Fungsi ubah(nama) untuk mengubah data berdasarkan nama.
- Buat Flowchart dan Penjelasan Programnya pada README.md.
- Commit dan push repository ke github.

#### Script

    dataMahasiswa = {}

    print("=" * 65)
    print("|\tPROGRAM INPUT NILAI MAHASISWA MENGGUNAKAN FUNGSI\t|")
    print("=" * 65)


    def tambah():
        nama = str(input("Masukan Nama : "))
        nim = int(input("Masukan Nim   : "))
        tugas = int(input("Masukan Nilai Tugas : "))
        uts = int(input("Masukan Nilai UTS     : "))
        uas = int(input("Masukan Nilai UAS     : "))
        akhir = (tugas / 3) + (uts / 3.5) + (uas / 3.5)
        dataMahasiswa[nama] = nim, tugas, uts, uas, akhir,
        print("\nDATA BERHASIL DITAMBAHKAN!")


    def tampilkan():
        print("=" * 69)
        print("|" + "\t" * 3 + "DAFTAR NILAI MAHASISWA" + "\t" * 3 +
              "    |")
        print("=" * 69)
        print("| NO |   \tNAMA\t   |\tNIM \t| TUGAS | UTS | UAS | AKHIR |")
        print("=" * 69)
        for tampil in dataMahasiswa.items():
            no = 0
            no += 1
            print("| {6:2} |\t {0:15}   | {1:9} \t| {2:5} | {3:3} | {4:3} | {5:5} |".format(tampil[0], tampil[1][0], tampil[1][1], tampil[1][2], tampil[1][3], "%.2f" % float(tampil[1][4]), no))
            print("=" * 69)

    def hapus(nama):
        del dataMahasiswa[nama]
        print("DATA BERHASIL DIHAPUS!")

    def ubah(nama):
        if nama in dataMahasiswa.keys():
            nim = int(input("Masukan Nim  : "))
            tugas = int(input("Masukan Nilai Tugas : "))
            uts = int(input("Masukan Nilai UTS     : "))
            uas = int(input("Masukan Nilai UAS     : "))
            akhir = (tugas / 3) + (uts / 3.5) + (uas / 3.5)
            dataMahasiswa[nama] = nim, tugas, uts, uas, akhir
            print("\nDATA BERHASIL DI UBAH!")
        else:
            print("\DATA TIDAK DITEMUKAN!")

    while True:
        data = input(
            "\n 1 - Tambahkan Data,\t 2 - Tampilkan Data,\t 3 - Hapus Data,\t 4 - Ubah Data, 5 - Keluar \n : "
        )
        if (data.lower() == '1'):
            tambah()

        elif (data.lower() == '4'):
            nama = str(input("Masukan Nama : "))
            ubah(nama)
        elif (data.lower() == '3'):
            nama = str(input("Masukan Nama : "))
            if nama in dataMahasiswa:
                hapus(nama)
            else:
                print("DATA TIDAK DITEMUKAN ".format(nama))
        elif (data.lower() == '2'):
            if dataMahasiswa.items():
                tampilkan()
            else:
                print("=" * 69)
                print("|" + "\t" * 3 + "DAFTAR NILAI MAHASISWA" + "\t" * 3 +
                      "    |")
                print("=" * 69)
                print("| NO |   \tNAMA\t   |\tNIM \t| TUGAS | UTS | UAS | AKHIR |")
                print("=" * 69)
                print("|    " + "\t" * 3 + "TIDAK ADA DATA!" + "\t" * 4 + "    |")
                print("=" * 69)
        elif (data.lower() == '5'):
            print("\nTERIMA KASIH! \n")
            exit()
        else:
            print("YANG ANDA CARI TIDAK ADA!")
            
![Screenshot (154)](https://user-images.githubusercontent.com/115794875/205833788-59e82340-d1b1-41af-bd70-1b8fae5e7ef9.png)
![Screenshot (155)](https://user-images.githubusercontent.com/115794875/205833987-a24af1ed-73bc-40ea-97b0-094d98ac07d6.png)
![Screenshot (156)](https://user-images.githubusercontent.com/115794875/205834222-8f54e4a5-6468-4072-8666-6b2885864f9f.png)
![Screenshot (157)](https://user-images.githubusercontent.com/115794875/205834356-b3392114-2259-4f37-91aa-01acd6197ec6.png)
    
#### Berikut hasil run
- Untuk menambahkan data kita perlu ketik angka 1 saja

  ![Screenshot (163)](https://user-images.githubusercontent.com/115794875/205834821-d3b0eeb7-826d-4ec2-93ec-23fbae7c98df.png)
    
- Menampilkan data ketik angka 2

  ![Screenshot (165)](https://user-images.githubusercontent.com/115794875/205835135-50e56622-de23-4b75-a490-ff2c5e9e096b.png)

- Untuk menghapus data dan keluar ketik angka 4 dan 5

  ![Screenshot (166)](https://user-images.githubusercontent.com/115794875/205835399-e85f2122-ca65-49ed-a0a6-d270eaa09c91.png)
    
#### Flowchart Praktikum

 ![image](https://user-images.githubusercontent.com/115794875/205836101-ecda7f0e-5de0-4e3f-a7ba-1d203c59b0a3.png)





