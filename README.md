# Gatherly – Modul 5: User Flow & Interaction Flow

Yonathan Hezron – 102042300161

Alur pendaftaran peserta untuk aplikasi Gatherly (Vue 3 + Vue Router + Vite).

## Menjalankan

```bash
npm install
npm run dev
```

## Flowchart Pendaftaran Workshop

```mermaid
flowchart TD
    A([Buka daftar event]) --> B[Pilih event & baca detail]
    B --> C{Cocok & mau daftar?}
    C -- Tidak --> A
    C -- Ya --> D[Buka form pendaftaran]
    D --> E[Isi data & tekan kirim]
    E --> F{Data lengkap & benar?}
    F -- Tidak --> G[Tampilkan pesan error spesifik per kolom] --> E
    F -- Ya --> H[Catat pendaftaran, kurangi kuota]
    H --> I([Modal Registration Confirmed + nomor referensi])
```

## Fitur

- `EventDetail` – tombol aksi berprioritas: Registration Closed → Already Registered (+ tautan tiket) → Sold Out → Register Now, memakai `router.push`.
- `EventRegistration` – layout dua kolom (`RegistrationSummary` + `RegistrationForm`), validasi per kolom, data valid tidak hilang saat error, dialog konfirmasi saat Cancel pada form yang sudah terisi.
- `AppModal` – named slot `footer`; `RegistrationReceipt` ditampilkan sebagai modal "Registration Confirmed".
- `EventCard` / `EventList` – lencana *Registered* reaktif.
- `YourEvents` & `TicketReceipt` – dompet tiket dan lembar tanda terima (rute `/browse/your-events` dan `/browse/your-events/:id`).
- `useEvents` – `registerAttendee`, `isUserRegistered`, `cancelRegistration`, dan penghapusan berantai tiket saat event dihapus; data tersimpan di `localStorage`.
- `main.css` – token `--space-5` (20px); `EventCreateForm` diselaraskan jaraknya.
