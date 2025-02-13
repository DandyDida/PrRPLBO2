package org.example;

public class STNK {
    private String pemilik;
    private String kodePlat;
    private String lokasi;

    // Konstruktor
    public STNK(String pemilik, String kodePlat) {
        this.pemilik = pemilik;
        this.kodePlat = ambilKodePlat(kodePlat);
        this.lokasi = getLokasiDariKode(this.kodePlat);
    }

    // Getter dan Setter
    public String getPemilik() {
        return pemilik;
    }

    public void setPemilik(String pemilik) {
        this.pemilik = pemilik;
    }

    public String getKodePlat() {
        return kodePlat;
    }

    public void setKodePlat(String kodePlat) {
        this.kodePlat = ambilKodePlat(kodePlat);
        this.lokasi = getLokasiDariKode(this.kodePlat);
    }

    public String getLokasi() {
        return lokasi;
    }

    // Metode untuk menentukan lokasi berdasarkan kode plat
    private String getLokasiDariKode(String kodePlat) {
        switch (kodePlat.toUpperCase()) {
            case "BE":
                return "Lampung";
            case "AB":
                return "Jogja";
            case "D":
                return "Bandung";
            case "B":
                return "Jakarta";
            default:
                return "Lokasi Tidak Diketahui";
        }
    }

    // Metode untuk mengambil kode plat dari input (mengambil dua huruf pertama)
    private String ambilKodePlat(String plat) {
        return plat.split(" ")[0]; // Mengambil dua huruf pertama dari plat
    }
}
