# CCNA-Level-Enterprise-Network

🚀 Proje İçeriği ve Teknik Detaylar
1. Temel Cihaz Güvenliği ve Yönetimi
SSH v2 Yapılandırması: Telnet yerine şifrelenmiş SSH v2 kullanılmıştır. Güvenlik için 1024 bitlik RSA anahtarları oluşturulmuş ve login local ile kullanıcı bazlı erişim sağlanmıştır.

Parola Güvenliği: enable secret (MD5) kullanılarak ayrıcalıklı mod güvenliği sağlanmış, service password-encryption ile tüm düz metin parolalar şifrelenmiştir.

Banner MOTD: Yetkisiz erişimlere karşı yasal uyarı mesajları eklenmiştir.

2. VLAN ve Inter-VLAN Routing
Neden VLAN?: Ağ trafiğini bölerek yayın (broadcast) trafiğini azaltmak, güvenliği artırmak ve departmanları birbirinden izole etmek için kullanılmıştır.

Mode Access & Trunk: Uç cihazlar için access, switchler arası trafik taşınması için 802.1Q trunking protokolü yapılandırılmıştır.

Router-on-a-Stick: Router üzerinde sub-interface'ler oluşturularak VLAN'lar arası haberleşme (Inter-VLAN Routing) sağlanmıştır.

3. Katman 2 Teknolojileri (EtherChannel & VTP)
EtherChannel (LACP/PAgP): Bant genişliğini artırmak ve yedeklilik sağlamak amacıyla fiziksel portlar grup haline getirilmiştir.

VTP (VLAN Trunking Protocol): Merkezi VLAN yönetimi için Server-Client yapısı kurulmuştur. Güvenlik amacıyla bazı switchler Transparent modda bırakılmıştır.

4. IP Yönetimi (DHCP & Relay Agent)
DHCP Server: Ağdaki cihazların otomatik IP alması sağlanmıştır.

DHCP Relay Agent: Farklı VLAN'lardaki cihazların merkezi DHCP sunucusuna erişebilmesi için ip helper-address yapılandırması uygulanmıştır.

5. Spanning Tree Protocol (STP) & Port Security
STP Optimization: Ağda döngü (loop) oluşmasını engellemek için Primary/Secondary Root Bridge atamaları yapılmıştır. Uç portlarda PortFast ve BPDUGuard etkinleştirilerek hızlı bağlantı ve güvenlik sağlanmıştır.

Port Security: MAC adresi tabanlı güvenlik uygulanmıştır. Beklenmedik bir MAC adresi algılandığında port otomatik olarak shutdown moduna geçecek şekilde yapılandırılmıştır.

6. Dinamik Yönlendirme (EIGRP)
EIGRP 100: Farklı lokasyonlardaki router'ların birbirini tanıması için EIGRP protokolü kullanılmıştır.

Passive Interface: Güvenlik ve bant genişliği tasarrufu için uç kullanıcıların olduğu interface'lerde yönlendirme güncellemeleri kapatılmıştır.

7. Güvenlik ve NAT/PAT
ACL (Access Control List): Trafik filtreleme yapılmıştır. (Örn: FTP erişimine izin verilirken, ICMP/Ping trafiği engellenmiştir).

PAT (Port Address Translation): Yerel ağdaki birçok cihazın tek bir genel (public) IP adresi üzerinden internete çıkması için overload yapılandırması yapılmıştır.

🛠 Kullanılan Donanımlar
Routers: 2911, 1841 (HWIC-2T Serial modüller ile)

Switches: 2960, 3560 Multilayer Switch

End Devices: PC, Laptop, Generic Servers





Cihazlar arasındaki bağlantıyı doğrulamak için Simulation Mode veya CLI üzerinden ping komutlarını kullanın.
