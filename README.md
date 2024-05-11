# Rooter-Golden-BaseIPK
Base IPK From Rooter GoldenOrb


= Install IPK Rooter =

Pastikan dulu sebelumnya belum pernah install ipk ext-rooter-basic. Kalau sudah pernah install ipk, sebaiknya install ipk di FW baru atau fw yang belum pernah install.
Karena ipk yang pernah saya buat sebelum belum saya edit, jadi ada notif konfirmasi setiap reboot di menu network interface, gak auto konek modemnya, harus klik konfirmasi dulu baru konek.

Sebelum install ipk rooter sebaiknya cek fw sudah install atinout belum, kelau belum bisa cari dan install.

Serta remove dulu ipk menu modem sebelumnya.

Terminal:

opkg remove 3ginfo 3ginfo-lite 3ginfo-text 3ginfo-qmisignal modeminfo modemband luci-app-3ginfo luci-app-3ginfo-lite luci-app-atinout luci-app-modemband luci-app-modeminfo luci-app-sms-tool --force-depends

= Eksekusi IPK Rooter =

Download semua ipk rooter dalam folder 21/22/23 *pilih sesuai FW

Upload file ipk ke folder /root file manager opewnrt

Terminal:

cd

opkg update && opkg install *.ipk --force-overwrite

Sesudah terinstall semua, remove ipk modemmanager luci-proto-modemmanager.

Teminal:

opkg remove modemmanager luci-proto-modemmanager --force-depends

Setelah teremove, remove juga interfaces modemmanager di menu network interfaces

Klik menu modem - Connection Profiles

Silahkan edit, apakah mau custom ttl value (pilih ttl 64/ttl 65).

Setelah diedit atau tidak, reboot device stb/sbc/x86

Tunggu sampai masuk luci, dan cek menu network interface. Interface wan1 akan otomatis detek modem rakitannya.

Kalau RX/TX interface modem tidak jalan/muncul coba reboot modem di menu modem - Miscellaneous, send command AT^RESET / AT+CFUN=1,1 untuk reboot modem.

Dan kalau interface tetap tidak jalan atau detek modem, silahkan reboot device stb/sbc/x86 lagi.
