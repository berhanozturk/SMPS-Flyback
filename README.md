# SMPS-Flyback
<img width="512" height="380" alt="mut-flyback" src="https://github.com/user-attachments/assets/0ed76696-7d19-49cc-a88b-e91d324784aa" /> 
<img width="512" height="380" alt="mut-flyback2" src="https://github.com/user-attachments/assets/4e79af9e-fa0e-4307-b5ef-e911df57514d" />


85-265 VAC giriş gerilimini sabit 24V 2.5A DC
çıkışa dönüştüren flyback topolojisine sahip
bir güç kaynağı devresi tasarlandı. KiCad ile
şematik ve baskı devre tasarımı yapıldı.

<img width="1556" height="624" alt="Screenshot 2025-07-14 170822" src="https://github.com/user-attachments/assets/ac989d68-de4a-4f23-a7d2-9c4e4b49c5b4" />

# FAN6751HLMY (PWM Kontrol Entegresi):
FAN6751HLMY’yi tercih ettim çünkü yüksek frekanslı (~100 kHz) sabit
PWM yapısıyla daha küçük trafo ve kompakt tasarım imkânı sunuyor
Green-mode ve burst-mode gibi düşük yükte güç tasarrufu sağlayan
özellikleri sayesinde enerji verimliliği yüksek bir tasarım için,
Dahili yüksek voltajlı startup devresi sayesinde harici direnç ihtiyacını
ortadan kaldırarak daha az bileşenle devreyi basitleştirdiği için,
Peak current mode kontrol yapısı ve dahili slope compensation
özelliğiyle sub-harmonik osilasyonları önlediği ve kararlı bir kontrol
sağladığı için tercih ettim.

# PC817 (Optokuplör):
PC817 optokuplörünü tercih ettim çünkü devremin alçak gerilimli
kontrol kısmıyla yüksek gerilimli güç kısmı arasında güvenli bir
izolasyon sağlamam gerekiyordu.
PC817, 5000 Vrms’e kadar izolasyon sağladığı için mikrodenetleyiciyi
olası yüksek gerilim risklerine karşı korumak amacıyla kullandım.
Düşük maliyetli, kolay bulunabilir ve DIP paketli olması nedeniyle
lehimleme ve devreye entegrasyonu kolay olduğu için PC817’yi
seçtim.
Giriş tarafında düşük sürücü akımı gerektirmesi ve çıkışta yeterli
akım sağlaması, bu optokuplörü enerji verimliliği yüksek bir tercih
haline getirdi.

# PQ3220S (Ferrit Trafo):
Bu boyuttaki bir çekirdek, yüksek güçte çalışacak uygulamalar için
ideal olduğundan ve bobin tasarımı açısından yaptığım hesaplamalar
sonucunda yeterli hacim sunduğundan PQ3220S’yi kullandım.

# Giriş Kapasitörleri (2x150μF):
Girişte 2x150μF elektrolitik kapasitör kullanmamın nedeni, AC–DC
doğrultma sonrası oluşan dalgalanmaları filtreleyerek sabit bir DC
gerilim elde etmek ve yüksek güçte giriş voltajındaki kararsızlıkları
sönümlemektir.

# 4.6 mH Giriş İndüktörü:
EMI (elektromanyetik girişim) bastırmak ve giriş akımını yumuşatmak
amacıyla kullanılır. Hem güvenlik hem EMC uyumu açısından
önemlidir.

# Çıkış Kapasitörleri (2x470μF):
2x470μF çıkış kapasitörünü, çıkışta düşük gerilim ripple’ı elde etmek
ve yük değişimlerine karşı gerilim stabilitesini korumak için tercih
ettim.

# IRF3205 (N-Kanal MOSFET):
IRF3205’i tercih ettim çünkü düşük R_DS(on) değeriyle anahtarlama
kayıplarını minimize ederek yüksek verimlilik sağlıyor.
Endüstriyel standartlarda yaygın bulunabilirliği ve uygun fiyatı,
IRF3205’i pratik ve ekonomik bir tercih haline getiriyor.
