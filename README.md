# PunyaKios PHP SDK

Official PHP SDK untuk memudahkan integrasi Merchant API PunyaKios.

## Instalasi

Cukup download file `PunyaKios.php` dan sertakan di project Anda:

```php
require_once 'PunyaKios.php';
```

## Penggunaan

```php
use PunyaKios\PunyaKios;

$sdk = new PunyaKios('YOUR_API_KEY');

// Create QRIS
$response = $sdk->createPaymentRequest([
    'external_id' => 'ORDER-101',
    'amount' => 10000,
    'description' => 'Pembayaran Kopi',
    'callback_url' => 'https://websitemu.com/callback.php'
]);

if ($response['status_code'] === 200) {
    echo "Checkout URL: " . $response['data']['data']['checkout_url'];
}
```

## Persyaratan
- PHP 7.4 atau lebih tinggi
- Ekstensi cURL diaktifkan

## Lisensi
MIT
