Untuk melakukan kalibrasi load cell dalam kode yang Anda berikan, Anda dapat mengikuti langkah-langkah berikut:

1. Tentukan berat yang diketahui. Anda memerlukan benda dengan berat yang diketahui (misalnya, 100 gram) untuk melakukan kalibrasi. Pastikan berat ini benar-benar diketahui dan akurat.

2. Dalam bagian `setup()`, Anda sudah memiliki kode untuk menetapkan berat yang diketahui sebagai skala awal dengan `scale.set_scale()`. Anda perlu memodifikasi kode ini untuk mengatur nilai yang sesuai dengan berat yang diketahui. Misalnya, jika berat yang diketahui adalah 100 gram, maka Anda dapat mengaturnya sebagai berikut:

   ```cpp
   scale.set_scale(100); // Set skala ke 100, sesuaikan dengan berat yang diketahui.
   ```

3. Kemudian, dalam `loop()`, Anda dapat melakukan pembacaan berat dengan menggunakan `scale.get_units()`. Berikut adalah bagian kode dalam `loop()` yang akan mencetak berat yang sesuai:

   ```cpp
   long reading = scale.get_units(10); // Membaca berat dalam 10 bacaan
   Serial.print("Result: ");
   Serial.println(reading);
   ```

4. Selanjutnya, saat Anda menjalankan kode ini, pastikan untuk menempatkan berat yang diketahui pada load cell ketika perintah "Place a known weight on the scale..." muncul di Serial Monitor. Bacaan yang diberikan oleh load cell harus sesuai dengan berat yang Anda tetapkan dalam `scale.set_scale()`.

5. Jika bacaan tidak sesuai, Anda mungkin perlu menyesuaikan nilai dalam `scale.set_scale()` hingga bacaan sesuai dengan berat yang diketahui.

6. Setelah kalibrasi berhasil, Anda dapat mengganti nilai dalam `scale.set_scale()` dengan berat yang diketahui dan menyimpannya sebagai nilai yang tepat.

Harap diingat bahwa hasil kalibrasi ini hanya berlaku untuk situasi saat itu dan dengan benda yang sama yang digunakan untuk kalibrasi. Jika Anda mengganti benda atau mengganti load cell, Anda mungkin perlu mengulangi proses kalibrasi.