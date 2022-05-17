# ADV160419047Week2
-- phpMyAdmin SQL Dump
-- version 5.0.4
-- https://www.phpmyadmin.net/
--
-- Host: localhost:3308
-- Generation Time: May 17, 2022 at 12:37 AM
-- Server version: 8.0.22
-- PHP Version: 8.0.2

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `apotikz`
--

-- --------------------------------------------------------

--
-- Table structure for table `buyers`
--

CREATE TABLE `buyers` (
  `id` bigint UNSIGNED NOT NULL,
  `name` varchar(100) NOT NULL,
  `address` varchar(200) NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

--
-- Dumping data for table `buyers`
--

INSERT INTO `buyers` (`id`, `name`, `address`, `created_at`, `updated_at`) VALUES
(1, 'Daniel', 'Sidoarjo', '2022-04-13 00:44:27', NULL),
(2, 'Lukita', 'Surabaya', '2022-04-13 00:44:27', NULL);

-- --------------------------------------------------------

--
-- Table structure for table `categories`
--

CREATE TABLE `categories` (
  `id` bigint UNSIGNED NOT NULL,
  `name` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `description` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Dumping data for table `categories`
--

INSERT INTO `categories` (`id`, `name`, `description`, `created_at`, `updated_at`) VALUES
(1, 'ANALGESIK NON NARKOTIK', '1.2. ANALGESIK NON NARKOTIK', NULL, NULL),
(2, 'ANTIPIRAI', '1.3. ANTIPIRAI', NULL, NULL),
(3, 'ANESTETIK LOKAL', '2.1 ANESTETIK LOKAL', NULL, NULL),
(4, 'ANTIMIGREN', '7.1 ANTIMIGREN', NULL, NULL),
(5, 'ANTIVERTIGO', '7.2 ANTIVERTIGO', NULL, NULL),
(6, 'IMUNOSUPRESAN', '8.2 IMUNOSUPRESAN', NULL, NULL),
(7, 'SITOTOKSIK', '8.3 SITOTOKSIK', NULL, NULL),
(8, 'DIURETIK', '15.1 DIURETIK', NULL, NULL),
(9, 'OBAT untuk HIPERTROFI PROSTAT', '15.2 OBAT untuk HIPERTROFI PROSTAT', NULL, NULL),
(10, 'HORMON ANTIDIURETIK', '16.1 HORMON ANTIDIURETIK', NULL, NULL),
(11, 'ANTIDIABETES', '16.2 ANTIDIABETES', NULL, NULL),
(12, 'TROMBOLITIK', '17.5 TROMBOLITIK', NULL, NULL);

-- --------------------------------------------------------

--
-- Table structure for table `failed_jobs`
--

CREATE TABLE `failed_jobs` (
  `id` bigint UNSIGNED NOT NULL,
  `connection` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `queue` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `payload` longtext CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `exception` longtext CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `failed_at` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Table structure for table `medicines`
--

CREATE TABLE `medicines` (
  `id` bigint UNSIGNED NOT NULL,
  `generic_name` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `form` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `restriction_formula` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `price` double(12,2) NOT NULL,
  `description` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `category_id` bigint UNSIGNED NOT NULL,
  `faskes1` tinyint(1) NOT NULL DEFAULT '0',
  `faskes2` tinyint(1) NOT NULL DEFAULT '0',
  `faskes3` tinyint(1) NOT NULL DEFAULT '0',
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL,
  `image` varchar(50) COLLATE utf8mb4_unicode_ci NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Dumping data for table `medicines`
--

INSERT INTO `medicines` (`id`, `generic_name`, `form`, `restriction_formula`, `price`, `description`, `category_id`, `faskes1`, `faskes2`, `faskes3`, `created_at`, `updated_at`, `image`) VALUES
(1, 'asam mefenamat', 'kaps 250 mg', '30 kaps/bulan.', 10000.00, '', 1, 1, 1, 1, NULL, NULL, 'asammefenamat250.jpg'),
(2, 'asam mefenamat', 'tab 500 mg', '30 tab/bulan.', 12000.00, '', 1, 1, 1, 1, NULL, NULL, 'asammefenamat500.jpg'),
(3, 'ibuprofen', 'tab 200 mg', '30 tab/bulan.', 8000.00, '', 1, 1, 1, 1, NULL, NULL, 'ibuprofen200.jpg'),
(4, 'ibuprofen', 'tab 400 mg', '30 tab/bulan.', 9500.00, '', 1, 1, 1, 1, NULL, NULL, 'ibuprofen400.jpg'),
(5, 'asam mefenamat', ' susp 100 mg/5 mL', '1 btl/kasus.', 15000.00, '', 1, 1, 1, 1, NULL, NULL, 'asammefenamat100.jpg'),
(6, 'ketoprofen', ' inj 50 mg/mL', '', 22000.00, 'Untuk nyeri sedang sampai berat pada pasien yang tidak', 1, 1, 1, 1, NULL, NULL, 'ketoprofen50.jpg'),
(7, 'ketoprofen', 'sup 100 mg', '2 sup/hari, maks 3 hari.', 25000.00, 'Untuk nyeri sedang sampai berat pada pasien yang tidak', 1, 1, 1, 1, NULL, NULL, 'ketoprofen100.jpg'),
(8, 'alopurinol', 'tab 100 mg', '30tab/bulan', 17500.00, 'Tidak diberikan pada saat nyeri akut', 2, 1, 1, 1, NULL, NULL, 'alopurinol100.jpg'),
(9, 'alopurinol', 'tab 300 mg', '30tab/bulan', 17500.00, 'Tidak diberikan pada saat nyeri akut', 2, 1, 1, 1, NULL, NULL, 'alopurinol300.jpg'),
(10, 'kolkisin', 'tab 500 mcg', '30tab/bulan', 16500.00, 'Tidak diberikan pada saat nyeri akut', 2, 1, 1, 1, NULL, NULL, 'kolkisin.jpg'),
(11, 'bupivakain', 'inj 0,5%', '', 12250.00, '', 3, 0, 1, 1, NULL, NULL, 'bupivakain.jpg'),
(12, 'lidokain', 'inj 0,5%', '', 12250.00, '', 3, 1, 1, 1, NULL, NULL, 'lidokain05.jpg'),
(13, 'lidokain', 'spray topikal 10%', '', 12250.00, '', 3, 1, 1, 1, NULL, NULL, 'lidokain10.jpg'),
(14, 'propranolol', 'tab 10 mg', '', 25250.00, '', 4, 1, 1, 1, NULL, NULL, 'propranolol.jpg'),
(15, 'betahistin', 'tab 6 mg', 'Untuk vertigo perifer:\n                - BPPV: 1 minggu.\n                - non BPPV: 30 \n                tab/bulan', 25250.00, 'Hanya untuk sindrom \n             meniere atau vertigo perifer.  Untuk sindrom meniere atau\n             vertigo non BPPV hanya di \n             Faskes Tk. 2 dan 3', 5, 1, 1, 1, NULL, NULL, 'betahistin6.jpg'),
(16, 'betahistin', 'tab 24 mg', '90 tab/bulan.n', 35000.00, 'Hanya untuk sindrom \n             meniere atau vertigo perifer.  Untuk sindrom meniere atau\n             vertigo non BPPV hanya di \n             Faskes Tk. 2 dan 3. Hanya untuk sindrom meniere', 5, 0, 1, 1, NULL, NULL, 'betahistin24.jpg');

-- --------------------------------------------------------

--
-- Table structure for table `medicine_transaction`
--

CREATE TABLE `medicine_transaction` (
  `medicine_id` bigint UNSIGNED NOT NULL,
  `transaction_id` bigint UNSIGNED NOT NULL,
  `quantity` int NOT NULL,
  `price` double NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

--
-- Dumping data for table `medicine_transaction`
--

INSERT INTO `medicine_transaction` (`medicine_id`, `transaction_id`, `quantity`, `price`) VALUES
(1, 1, 2, 10000),
(3, 2, 3, 8000),
(8, 1, 1, 17500),
(10, 3, 2, 16500),
(12, 3, 4, 12250),
(14, 3, 1, 25250);

-- --------------------------------------------------------

--
-- Table structure for table `migrations`
--

CREATE TABLE `migrations` (
  `id` int UNSIGNED NOT NULL,
  `migration` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `batch` int NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Dumping data for table `migrations`
--

INSERT INTO `migrations` (`id`, `migration`, `batch`) VALUES
(7, '2014_10_12_000000_create_users_table', 1),
(8, '2014_10_12_100000_create_password_resets_table', 1),
(9, '2019_08_19_000000_create_failed_jobs_table', 1),
(22, '2022_02_22_041604_create_products_table', 2),
(23, '2022_02_22_041646_create_categories_table', 2),
(24, '2022_02_22_042758_add_categoryid_column', 2),
(25, '2022_02_22_050908_create_medicines_table', 2),
(26, '2022_03_01_031502_update_foreignkey_medicine', 2);

-- --------------------------------------------------------

--
-- Table structure for table `password_resets`
--

CREATE TABLE `password_resets` (
  `email` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `token` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Table structure for table `products`
--

CREATE TABLE `products` (
  `id` bigint UNSIGNED NOT NULL,
  `product_name` varchar(200) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `product_price` bigint NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL,
  `category_id` bigint UNSIGNED NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Table structure for table `suppliers`
--

CREATE TABLE `suppliers` (
  `id` bigint UNSIGNED NOT NULL,
  `name` varchar(100) NOT NULL,
  `address` varchar(200) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

--
-- Dumping data for table `suppliers`
--

INSERT INTO `suppliers` (`id`, `name`, `address`) VALUES
(1, 'Fisika Farma', 'Raya Kalirungkut'),
(2, 'kopimex', 'Sragen'),
(7, 'Biologio Farma', 'Denpasar'),
(8, 'Kaldu Farma', 'Jogja'),
(9, 'KalCe Farma', 'Semarang'),
(10, 'KalDe Farma', 'Jombang'),
(13, 'Kalfe Farma', 'Jogja');

-- --------------------------------------------------------

--
-- Table structure for table `transactions`
--

CREATE TABLE `transactions` (
  `id` bigint UNSIGNED NOT NULL,
  `buyer_id` bigint UNSIGNED NOT NULL,
  `user_id` bigint UNSIGNED NOT NULL,
  `transaction_date` datetime NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

--
-- Dumping data for table `transactions`
--

INSERT INTO `transactions` (`id`, `buyer_id`, `user_id`, `transaction_date`, `created_at`, `updated_at`) VALUES
(1, 1, 6, '2022-04-13 07:46:16', '2022-04-13 00:46:16', NULL),
(2, 2, 6, '2022-04-14 07:46:16', NULL, NULL),
(3, 1, 6, '2022-04-15 07:47:37', NULL, NULL);

-- --------------------------------------------------------

--
-- Table structure for table `users`
--

CREATE TABLE `users` (
  `id` bigint UNSIGNED NOT NULL,
  `name` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `email` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `email_verified_at` timestamp NULL DEFAULT NULL,
  `password` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `remember_token` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Dumping data for table `users`
--

INSERT INTO `users` (`id`, `name`, `email`, `email_verified_at`, `password`, `remember_token`, `created_at`, `updated_at`) VALUES
(1, 'bIaIahyai4', 'zTAgcNxSUK@gmail.com', NULL, '$2y$10$kt1wzicIrYrJlXRJduWqeetRHW/4/IBzXK/gv8rkfIbPgysX/blPC', NULL, NULL, NULL),
(2, 'GR72LbeGIT', 'TUnW716bRQ@gmail.com', NULL, '$2y$10$8evIfEONvroyEAyjlYgTUu9qiI6UqWX9wblj55awD1bfLY3qFOctK', NULL, NULL, NULL),
(3, 'E9LIo1Mt5Y', 'G2hpDHYseW@gmail.com', NULL, '$2y$10$cI7kLnKIg2tr9YY5fqpfpuJ9kbzZDwEnN6uxKo7BvSRLuicdjCLrC', NULL, NULL, NULL),
(4, 'Os3L5CP2dO', 'zvfpPMmYlK@gmail.com', NULL, '$2y$10$AxS76Q.SIwjpz16KqT3y4uohTkv63.OY4/Z7y1LZDbUkl.2cYp2n6', NULL, NULL, NULL),
(5, '98jzfh3aZ7', 'YgiemmmNfU@gmail.com', NULL, '$2y$10$IRN/jzWV2Z0MOvAY.gqsIeXLwYNlgPUdWHbKSJz0uBuYemeX9IWom', NULL, NULL, NULL),
(6, 'Admin', 'admin@gmail.com', NULL, '$2y$10$8KQzXn1Wud0Q7iSqUSw6RufO52VbXjGAuoI1ZazkqlrNpZtyUc2HW', NULL, NULL, NULL);

--
-- Indexes for dumped tables
--

--
-- Indexes for table `buyers`
--
ALTER TABLE `buyers`
  ADD PRIMARY KEY (`id`);

--
-- Indexes for table `categories`
--
ALTER TABLE `categories`
  ADD PRIMARY KEY (`id`);

--
-- Indexes for table `failed_jobs`
--
ALTER TABLE `failed_jobs`
  ADD PRIMARY KEY (`id`);

--
-- Indexes for table `medicines`
--
ALTER TABLE `medicines`
  ADD PRIMARY KEY (`id`),
  ADD KEY `medicines_category_id_foreign` (`category_id`);

--
-- Indexes for table `medicine_transaction`
--
ALTER TABLE `medicine_transaction`
  ADD PRIMARY KEY (`medicine_id`,`transaction_id`),
  ADD KEY `medicine_transaction_transaction_id_foreign` (`transaction_id`);

--
-- Indexes for table `migrations`
--
ALTER TABLE `migrations`
  ADD PRIMARY KEY (`id`);

--
-- Indexes for table `password_resets`
--
ALTER TABLE `password_resets`
  ADD KEY `password_resets_email_index` (`email`);

--
-- Indexes for table `products`
--
ALTER TABLE `products`
  ADD PRIMARY KEY (`id`),
  ADD KEY `products_category_id_foreign` (`category_id`);

--
-- Indexes for table `suppliers`
--
ALTER TABLE `suppliers`
  ADD PRIMARY KEY (`id`);

--
-- Indexes for table `transactions`
--
ALTER TABLE `transactions`
  ADD PRIMARY KEY (`id`),
  ADD KEY `transactions_buyer_id_foreign` (`buyer_id`),
  ADD KEY `transactions_user_id_foreign` (`user_id`);

--
-- Indexes for table `users`
--
ALTER TABLE `users`
  ADD PRIMARY KEY (`id`),
  ADD UNIQUE KEY `users_email_unique` (`email`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `buyers`
--
ALTER TABLE `buyers`
  MODIFY `id` bigint UNSIGNED NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;

--
-- AUTO_INCREMENT for table `categories`
--
ALTER TABLE `categories`
  MODIFY `id` bigint UNSIGNED NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=13;

--
-- AUTO_INCREMENT for table `failed_jobs`
--
ALTER TABLE `failed_jobs`
  MODIFY `id` bigint UNSIGNED NOT NULL AUTO_INCREMENT;

--
-- AUTO_INCREMENT for table `medicines`
--
ALTER TABLE `medicines`
  MODIFY `id` bigint UNSIGNED NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=17;

--
-- AUTO_INCREMENT for table `migrations`
--
ALTER TABLE `migrations`
  MODIFY `id` int UNSIGNED NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=27;

--
-- AUTO_INCREMENT for table `products`
--
ALTER TABLE `products`
  MODIFY `id` bigint UNSIGNED NOT NULL AUTO_INCREMENT;

--
-- AUTO_INCREMENT for table `suppliers`
--
ALTER TABLE `suppliers`
  MODIFY `id` bigint UNSIGNED NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=14;

--
-- AUTO_INCREMENT for table `transactions`
--
ALTER TABLE `transactions`
  MODIFY `id` bigint UNSIGNED NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=4;

--
-- AUTO_INCREMENT for table `users`
--
ALTER TABLE `users`
  MODIFY `id` bigint UNSIGNED NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=8;

--
-- Constraints for dumped tables
--

--
-- Constraints for table `medicines`
--
ALTER TABLE `medicines`
  ADD CONSTRAINT `medicines_category_id_foreign` FOREIGN KEY (`category_id`) REFERENCES `categories` (`id`);

--
-- Constraints for table `medicine_transaction`
--
ALTER TABLE `medicine_transaction`
  ADD CONSTRAINT `medicine_transaction_medicine_id_foreign` FOREIGN KEY (`medicine_id`) REFERENCES `medicines` (`id`),
  ADD CONSTRAINT `medicine_transaction_transaction_id_foreign` FOREIGN KEY (`transaction_id`) REFERENCES `transactions` (`id`);

--
-- Constraints for table `products`
--
ALTER TABLE `products`
  ADD CONSTRAINT `products_category_id_foreign` FOREIGN KEY (`category_id`) REFERENCES `categories` (`id`);

--
-- Constraints for table `transactions`
--
ALTER TABLE `transactions`
  ADD CONSTRAINT `transactions_buyer_id_foreign` FOREIGN KEY (`buyer_id`) REFERENCES `buyers` (`id`),
  ADD CONSTRAINT `transactions_user_id_foreign` FOREIGN KEY (`user_id`) REFERENCES `users` (`id`);
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
