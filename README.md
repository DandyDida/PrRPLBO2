# PrRPLBO2

class STNK

public class STNK {
    private String pemilik;
    private String kodePlat;
    private String lokasi;

    // Konstruktor
    public STNK(String pemilik, String kodePlat) {
        this.pemilik = pemilik;
        this.kodePlat = kodePlat;
        this.lokasi = tentukanLokasi(kodePlat);
    }

    // Metode untuk menentukan lokasi berdasarkan kode plat
    private String tentukanLokasi(String kodePlat) {
        if (kodePlat.startsWith("BE")) {
            return "Lampung";
        } else if (kodePlat.startsWith("AB")) {
            return "Jogja";
        } else if (kodePlat.startsWith("D")) {
            return "Bandung";
        } else if (kodePlat.startsWith("B")) {
            return "Jakarta";
        } else {
            return "Tidak Diketahui";
        }
    }

    // Getter
    public String getPemilik() {
        return pemilik;
    }

    public String getKodePlat() {
        return kodePlat;
    }

    public String getLokasi() {
        return lokasi;
    }

    // Setter
    public void setPemilik(String pemilik) {
        this.pemilik = pemilik;
    }

    public void setKodePlat(String kodePlat) {
        this.kodePlat = kodePlat;
        this.lokasi = tentukanLokasi(kodePlat);
    }

    // Method untuk menampilkan STNK
    public void printSTNK() {
        System.out.println("Nama        : " + pemilik);
        System.out.println("Kode Plat   : " + kodePlat);
        System.out.println("Lokasi      : " + lokasi);
    }
}




2 2 2

class main 

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input nama pemilik
        System.out.print("Masukkan nama Anda: ");
        String nama = scanner.nextLine();

        // Input plat nomor
        System.out.print("Masukkan plat nomer Anda: ");
        String platNomor = scanner.nextLine();

        // Membuat objek STNK
        STNK stnk = new STNK(nama, platNomor);

        // Menampilkan data STNK
        System.out.println();
        stnk.printSTNK();

        scanner.close();
    }
}
