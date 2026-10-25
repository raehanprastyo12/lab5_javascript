## H. Pertanyaan dan Tugas

### 1. Perbedaan `console.log()`, `alert()`, `prompt()`, dan `textContent`/`innerHTML`

- `console.log()`: Menampilkan pesan atau data di console browser, biasanya untuk debugging.
  javascript
  ```
  console.log("Halo Dunia!");
  ```
- `alert()`: Menampilkan pesan dalam kotak dialog yang harus ditutup oleh pengguna.
  javascript
  ```
  alert("Selamat datang!");
  ```
- `prompt()`: Menampilkan kotak dialog untuk meminta masukan dari pengguna.
  javascript
  ```
  let nama = prompt("Masukkan nama Anda:");
  ```
- `textContent`: Mengubah atau mengambil teks dari elemen HTML tanpa memproses tag HTML.
  javascript
  ```
  document.getElementById("hasil").textContent = "Halo!";
  ```
- `innerHTML`: Mengubah atau mengambil isi elemen HTML, termasuk tag HTML.
  javascript
  ```
  document.getElementById("hasil").innerHTML = "<b>Halo!</b>";
  ```

### 2. Perbedaan `let` dan `const`

- `let` digunakan untuk membuat variabel yang nilainya dapat diubah.
- `const` digunakan untuk membuat variabel yang tidak dapat diberi nilai ulang setelah deklarasi.

Contoh:

javascript

```
let umur = 17;
umur = 18;

const nama = "Andi";
// nama = "Budi"; // Akan menghasilkan error

console.log(umur);
console.log(nama);
```

### 3. Perbedaan operator `==` dan `===`

- `==` (sama dengan) membandingkan nilai dengan memungkinkan konversi tipe data.
- `===` (strict equality) membandingkan nilai sekaligus tipe datanya.

Contoh:

javascript

```
console.log(5 == "5");  // true
console.log(5 === "5"); // false
```

Operator `===` lebih disarankan agar perbandingan lebih jelas dan menghindari konversi tipe data yang tidak diinginkan.

### 4. Fungsi `if–else` dan `switch`

`if–else` digunakan untuk menjalankan kode berdasarkan kondisi tertentu. Cocok untuk kondisi yang menggunakan perbandingan atau beberapa syarat.

Contoh:

javascript

```
let nilai = 85;

if (nilai >= 75) {
    console.log("Lulus");
} else {
    console.log("Tidak lulus");
}
```

`switch` digunakan untuk memilih salah satu tindakan berdasarkan nilai tertentu yang cocok dengan beberapa pilihan kasus.

Contoh:

javascript

```
let hari = 1;

switch (hari) {
    case 1:
        console.log("Senin");
        break;
    case 2:
        console.log("Selasa");
        break;
    default:
        console.log("Hari tidak diketahui");
}
```

`if–else` lebih cocok untuk kondisi rentang nilai atau gabungan beberapa syarat, sedangkan `switch` cocok untuk pilihan dengan nilai tertentu, seperti menu atau nama hari.

### 5. Fungsi parameter dan `return` dalam function

- Parameter adalah variabel yang digunakan untuk menerima data atau masukan ke dalam fungsi.
- `return` digunakan untuk mengembalikan hasil dari fungsi kepada bagian kode yang memanggilnya.

Contoh:

javascript

```
function tambah(a, b) {
    return a + b;
}

let hasil = tambah(5, 3);
console.log(hasil); // 8
```

Pada contoh tersebut, `a` dan `b` adalah parameter, sedangkan `return a + b` mengembalikan hasil penjumlahan.

### 6. Cara JavaScript memilih elemen HTML dengan `document.getElementById()`

`document.getElementById()` digunakan untuk memilih elemen HTML berdasarkan atribut `id` yang dimilikinya. ID tersebut harus sesuai dengan ID elemen yang ingin dipilih.

Contoh HTML:

HTMLWrap linesCopy codePreview

```
<p id="pesan">Teks awal</p>
```

Contoh JavaScript:

javascript

```
document.getElementById("pesan").textContent = "Teks baru";
```

Hasilnya, teks pada elemen tersebut berubah menjadi Teks baru. Jika tidak ada elemen dengan ID yang sesuai, metode ini akan mengembalikan `null`.

### 7. Script untuk memvalidasi form agar nama tidak kosong dan nilai berada pada rentang 0–100

Berikut contoh HTML dan JavaScript untuk memvalidasi nama dan nilai sebelum data diproses.

HTMLWrap linesCopy codePreview

```

<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Validasi Form</title>
</head>
<body>
    <h2>Form Data Siswa</h2>

    <form id="formSiswa">
        <label for="nama">Nama:</label>
        <input type="text" id="nama">
        <br><br>

        <label for="nilai">Nilai:</label>
        <input type="number" id="nilai">
        <br><br>

        <button type="submit">Kirim</button>
    </form>

    <p id="hasil"></p>

    <script>
        document.getElementById("formSiswa")
            .addEventListener("submit", function(event) {
                event.preventDefault();

                let nama = document.getElementById("nama")
                    .value.trim();
                let nilaiInput = document.getElementById("nilai")
                    .value;
                let nilai = Number(nilaiInput);
                let hasil = document.getElementById("hasil");

                if (nama === "") {
                    hasil.textContent = "Nama tidak boleh kosong!";
                } else if (
                    nilaiInput.trim() === "" ||
                    !Number.isFinite(nilai) ||
                    nilai < 0 ||
                    nilai > 100
                ) {
                    hasil.textContent =
                        "Nilai harus berada pada rentang 0–100!";
                } else {
                    hasil.textContent =
                        "Data valid. Nama: " + nama +
                        ", Nilai: " + nilai;
                }
            });
    </script>
</body>
</html>
```

Penjelasan:

1. `getElementById()` digunakan untuk mengambil elemen form, nama, nilai, dan hasil.
2. `value.trim()` digunakan untuk mengambil nama sekaligus menghapus spasi di awal dan akhir.
3. `event.preventDefault()` mencegah form dikirim secara otomatis sebelum validasi selesai.
4. `if–else` memeriksa apakah nama kosong dan apakah nilai berada di luar rentang 0–100.
5. Jika semua syarat terpenuhi, pesan bahwa data valid akan ditampilkan pada elemen dengan ID `hasil`.

Kesimpulan: JavaScript dapat digunakan untuk menampilkan informasi, menyimpan data dalam variabel, melakukan perbandingan, menentukan alur program, membuat fungsi, memilih elemen HTML, serta memvalidasi masukan pengguna sebelum diproses.