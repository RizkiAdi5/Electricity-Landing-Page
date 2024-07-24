# database
MariaDB [TokenListrik]> CREATE TABLE profile (
    ->     user_id INT PRIMARY KEY,
    ->     username VARCHAR(50) NOT NULL,
    ->     email VARCHAR(100) NOT NULL,
    ->     password VARCHAR(100) NOT NULL,
    ->     full_name VARCHAR(100) NOT NULL,
    ->     address VARCHAR(255),
    ->     phone_number VARCHAR(20),
    ->     foto_profil VARCHAR(255), -- Kolom untuk menyimpan path atau URL foto profil
    ->     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    -> );
Query OK, 0 rows affected (0.024 sec)

MariaDB [TokenListrik]> CREATE TABLE transaksi_token_listrik (
    ->     transaksi_id INT PRIMARY KEY,
    ->     user_id INT,
    ->     username VARCHAR(50),
    ->     nomor_meteran VARCHAR(50),
    ->     tanggal_transaksi DATE,
    ->     jumlah_token DECIMAL(10, 2),
    ->     metode_pembayaran VARCHAR(50),
    ->     status_transaksi VARCHAR(20),
    ->     nomor_token VARCHAR(20), -- Kolom untuk menyimpan nomor token yang tergenerate secara otomatis
    ->     FOREIGN KEY (user_id) REFERENCES profile(user_id)
    -> );