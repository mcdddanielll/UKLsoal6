# UKLsoal6[UKL6.java](https://github.com/user-attachments/files/23922817/UKL6.java)
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 */

package com.mycompany.ukl6;

import java.util.Scanner;

public class UKL6 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("=== PROGRAM HITUNG BIAYA PEMINJAMAN BUKU ===");
        
        System.out.print("Nama peminjam: ");
        String namaPeminjam = scanner.nextLine();
        
        System.out.print("Judul buku: ");
        String judulBuku = scanner.nextLine();
        
        System.out.print("Kategori buku (A/B/C): ");
        String kategori = scanner.nextLine().toUpperCase();
        
        System.out.print("Lama peminjaman (hari): ");
        int lamaPeminjaman = scanner.nextInt();
        
        int tarifPerHari = 0;
        String namaKategori = "";
        
        switch (kategori) {
            case "A":
                tarifPerHari = 2000;
                namaKategori = "Buku Pelajaran / Referensi";
                break;
            case "B":
                tarifPerHari = 1500;
                namaKategori = "Novel / Komik";
                break;
            case "C":
                tarifPerHari = 1000;
                namaKategori = "Majalah / Buku Umum";
                break;
            default:
                System.out.println("Kategori tidak valid. Harap masukkan A, B, atau C.");
                scanner.close();
                return;
        }
      
        int biayaAwal = tarifPerHari * lamaPeminjaman;
        
        int denda = 0;
        if (lamaPeminjaman > 7) {
            int hariTerlambat = lamaPeminjaman - 7;
            denda = 500 * hariTerlambat;
        }
        
        int totalBiaya = biayaAwal + denda;
        
        System.out.println("\n=== RINCIAN PEMINJAMAN ===");
        System.out.println("Nama peminjam      : " + namaPeminjam);
        System.out.println("Judul buku         : " + judulBuku);
        System.out.println("Kategori buku      : " + namaKategori + " (Kategori " + kategori + ")");
        System.out.println("Lama peminjaman    : " + lamaPeminjaman + " hari");
        System.out.println("Biaya peminjaman awal : Rp " + biayaAwal);
        System.out.println("Denda keterlambatan   : Rp " + denda);
        System.out.println("Total biaya akhir     : Rp " + totalBiaya);
        
    }
}
