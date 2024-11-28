# Exercise 4 - Gain a good understanding of task behaviour where a priority preemptive scheduling policy is used.
Latihan ini bertujuan untuk memahami bagaimana sistem operasi real-time (RTOS) menangani multitasking dengan kebijakan penjadwalan preemptive priority. Pada bagian ini akan mengamati bagaimana tugas-tugas dengan prioritas berbeda memengaruhi urutan eksekusi dalam sistem berbasis STM32 dan FreeRTOS.
## Tujuan
1. Memahami konsep preemptive scheduling di FreeRTOS.
2. Mengamati bagaimana prioritas tugas memengaruhi eksekusi dan interupsi antar tugas.
3. Mempraktikkan pembuatan tugas (task) dengan FreeRTOS pada STM32.

## Peralatan

1. STM32F103C8T
2. LED
3. Kabel Jummper
4. Mini debugger
## Langkah Implementasi

1. Konfigurasi STM32CubeMX: Pilih board STM32F103C
2. Aktifkan FreeRTOS dari tab Middleware.
3. Konfigurasikan GPIO untuk LED: GPIOA Pin 8: Red LED. GPIOA Pin 9: Green LED. GPIOA Pin 10: Orange LED (indikator tugas). GPIOA Pin 11: Blue LED (opsional untuk debugging). Generate kode untuk STM32CubeIDE atau Keil uVision.
4. Implementasi Kode Tugas: Tambahkan kode untuk tugas berikut: - Tugas 1 (Green LED): Prioritas: Normal. Berkedip 80 kali setiap 50 ms, diikuti dengan delay 6 detik. - Tugas 2 (Red LED): Prioritas: Above Normal. Berkedip 10 kali setiap 50 ms, diikuti dengan delay 1,5 detik. Gunakan fungsi FreeRTOS seperti osThreadNew() untuk membuat tugas dan vTaskDelay() untuk mengatur jeda.
5. Kompilasi dan Upload: Kompilasi kode menggunakan STM32CubeIDE atau Keil uVision. Flash ke board STM32.
6. Pengamatan: Perhatikan bagaimana Green LED berkedip lebih lambat dibanding Red LED. Red LED akan menginterupsi eksekusi Green LED karena memiliki prioritas lebih tinggi.
## Hasil yang Diharapkan
Green LED: Berkedip 80 kali setiap 50 ms, lalu delay 6 detik. Sering diinterupsi oleh Red LED, sehingga terlihat lebih lambat.
Red LED: Berkedip 10 kali setiap 50 ms, lalu delay 1,5 detik. Selalu memiliki prioritas lebih tinggi dibanding Green LED.
Indikator Blue/Orange LED: Blue LED menyala selama Green LED berjalan. Orange LED menyala selama Red LED berjalan.
## Hasil Percobaan


https://github.com/user-attachments/assets/e1ec3c59-8e80-4d72-8fed-6e1110dc985b
