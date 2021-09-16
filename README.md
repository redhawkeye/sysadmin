# Panduan keamanan untuk seorang sysadmin

# 1.	Meminimalisir serangan dos/ddos pada server	
- [ ]	Blok traffic masuk ICMP
- [ ]	Blok IP yang di sinyalir membahayakan server dengan iptables
- [ ]	Batasi jumlah traffic masuk pada server
- [ ]	Tutup port yang tidak di perlukan
- [ ]	Batasi ukuran file yang di upload
- [ ]	Pasang IDS & IPS untuk meminimalisir serangan
# 2.	Menangkal serangan bruteforce	
- [ ]	Jangan izinkan user root masuk ke dalam ssh atau gunakan user biasa untuk login ke ssh
- [ ]	Gunakan private key yang di password untuk login ke ssh
- [ ]	Ganti port default ssh menjadi port random
- [ ]	Batasi pengecekan password yang salah dengan fail2ban
- [ ]	Usahakan password yang di gunakan tidak mudah di tebak
- [ ]	Segala hal yang berhubungan dengan password harus di bedakan
# 3.	Meningkatkan keamanan pada aplikasi yang di pakai	
- [ ]	Enkripsi setiap script config database yang di gunakan di server atau pindahkan ke folder yang tidak biasanya
- [ ]	Gunakan ssl di dalam webserver
- [ ]	Jangan simpan private key di dalam server
- [ ]	Jangan simpan file backup di dokumen publik webserver
- [ ]	Rubah alamat phpmyadmin jadi alamat acak
- [ ]	Rubah alamat login admin jadi alamat acak
- [ ]	Gunakan OTP untuk login ke dalam aplikasi 
- [ ]	Filter semua POST dan GET yang ada dalam aplikasi
# 4.	Meningkatkan keamana jaringan pada server	
- [ ]	Batasi koneksi outgoing menggunakan iptables
- [ ]	Nonaktifkan DNS di /etc/resolv.conf
- [ ]	Hanya izinkan port yang terbuka saja yang bisa di akses publik menggunakan ufw/iptables
- [ ]	Jangan buka port database ke publik
- [ ]	Gunakan 1 ip gateway, 1 ip netmask, 1 ip broadcast, 1 ip address, dan 1 vlan untuk 1 aplikasi
# 5.	Meningkatkan keamanan pada server	
- [ ]	Selalu update system operasi yang sedang di gunakan
- [ ]	Sembunyikan versi PHP, apache, dll di header
- [ ]	Non aktifkan directory listing di webserver
- [ ]	Disable shell pada user web server "www-data" di /etc/passwd
- [ ]	Non aktifkan fungsi execute command seperti exec, passthru, php-cgi kalo tidak di perlukan
- [ ]	Di history command jangan tertinggal password apapun
# 6.	Monitoring server untuk meningkatkan keamanan	
- [ ]	Selalu cek log aktivitas server (monitoring)
- [ ]	Cek cronjob atau crontab setiap waktu di setiap user
- [ ]	Cek setiap service yang berjalan agar tidak terjadi misconfigurasi
- [ ]	Pasang alamat admin palsu (honeypot)
