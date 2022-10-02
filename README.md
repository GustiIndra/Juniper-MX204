# Juniper-MX204
Configure Actived / Deactived Routing Instans

Cara Active/Deative Routing instancs di MX

1. Show interface ae berapa untuk mengetahui description yang di pakai di mx tersebut
2. ketik comand " deactivate routing-instances [ Nama routing instans / description ]
3. Pastikan routing instances  sudah benar dengan ketik " show | compare "
4. Jika sudah benar lalu " commit check " jika tidak ada eror maka lanjut " commit "
5. setelah itu ketik " activate routing-instances [ Nama routing instans / description ]
dan pastikan routing instances sesuai lalu commit check dan commit 


Example:

gusti@MX-MR202# show interfaces ae11 unit 2942    
description SDI-nusantara-timur;
encapsulation vlan-bridge;
vlan-id 2942;
input-vlan-map pop;
output-vlan-map push;
family bridge;

gusti@MX-MR202# deactivate routing-instances SDI-nusantara-timur

gusti@MX-MR202# show | compare
[edit routing-instances]
! inactive: SDI-nusantara-timur { ... }

[edit]
gusti@MX-MR202# commit check
configuration check succeeds

[edit]
gusti@MX-MR202# commit
commit complete

======================

gusti@MX-MR202# activate routing-instances SDI-nusantara-timur

[edit]
gusti@MX-MR202# show | compare
[edit routing-instances]
! active: SDI-nusantara-timur { ... }
co
[edit]
gusti@MX-MR202# commit check
configuration check succeeds

[edit]
gusti@MX-MR202# commit
commit complete

[edit]
gusti@MX-MR202#

