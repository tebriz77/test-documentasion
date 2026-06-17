# Proqram Təminatının Test Hesabatı (Test Log)

Bu sənəd tətbiq üzərində aparılmış **Exploratory (Kəşfiyyat)** və **Ad-Hoc / Monkey** testlərinin nəticələrini özündə əks etdirir.

## 📊 Test Xülasəsi (Summary)

| Test Növü | Cəmi Test | Keçib (PASS) | Qalıb (FAIL) | Keçid Faizi (%) |
| :--- | :---: | :---: | :---: | :---: |
| **Exploratory Testing** | 7 | 4 | 3 | 57.1% |
| **Ad-Hoc / Monkey Testing** | 6 | 4 | 2 | 66.6% |
| **CƏMİ** | **13** | **8** | **5** | **61.5%** |

---

## 🔍 1. EXPLORATORY TESTING (Kəşfiyyat Testi)

Kəşfiyyat testləri zamanı tətbiqin əsas funksionallığı, naviqasiya strukturu və istifadəçi interfeysi (UI) yoxlanılmışdır.

| ID | CHECKPOINT (Yoxlama Nöqtəsi) | EXPECTED RESULT (Gözlənilən Nəticə) | ACTUAL RESULT (Faktiki Nəticə) | STATUS |
| :--- | :--- | :--- | :--- | :---: |
| **CL-01** | Tətbiqin açılışı | Tətbiq loqo ilə aydın açılmalı və ana səhifəyə keçməlidir. | Tətbiq loqo ilə problemsiz açıldı və səhifə göründü. | **🔴 PASS** |
| **CL-02** | Əsas menyu və tablar arası keçid | Alt menyudakı bütün keçidlər kliklənən olmalı və düzgün səhifəni açmalıdır. | Alt menyudakı “home”, “courses”, “tasks”, “grades” və “profile” düymələri açır. | **🔴 PASS** |
| **CL-03** | Vizual elementlərin və yazıların nizamı | Şəkillər, mətnlər və düymələr səliqəli görünməli, bir-birinin üzərinə düşməməlidir. | İnterfeys elementləri ekrana tam yerləşir və səliqəli görünür. | **🔴 PASS** |
| **CL-04** | Kurs kartlarına keçid funksiyası | Kursun üzərinə kliklədikdə materiallar açılmalıdır. | Həm “home”, həm də “courses” səhifəsində kurs kartlarına klik etdikdə heç nə açılmır. | **❌ FAIL** |
| **CL-05** | “See all” düymələrini klik etmək | “See all” yazısına kliklədikdə müvafiq bölmənin tam siyahısı açılmalıdır. | Düyməyə basdıqda heç bir reaksiya baş vermir və səhifə açılmır. | **❌ FAIL** |
| **CL-06** | Çıxış ssenarisi | Sistemdən çıxış etdikdən sonra istifadəçi məlumatları silinməli və giriş səhifəsinə yönləndirilməlidir. | Profil səhifəsindəki 3 nöqtəyə klik edib "sign out" düyməsinə klik etdikdə əsas səhifəyə yönləndirilir. | **🔴 PASS** |
| **CL-07** | Təkrar giriş etmək | Mövcud e-poçt yazıldıqda və "forgot password"a klik etdikdə gmail-ə mesaj göndərilməli və şifrə sıfırlama bölməsindən şifrəni dəyişmək mümkün olmalıdır. | Gmail-ə mesaj göndərildi, lakin "forgot reset" linkinə klik etdikdə status code 422 xətası verir. | **❌ FAIL** |

---

## ⚡ 2. AD-HOC / MONKEY TESTING

Bu mərhələdə tətbiqin gözlənilməz istifadəçi hərəkətlərinə, sistem kəsintilərinə və stress hallarına qarşı dayanıqlığı yoxlanılmışdır.

| ID | CHECKPOINT (Yoxlama Nöqtəsi) | EXPECTED RESULT (Gözlənilən Nəticə) | ACTUAL RESULT (Faktiki Nəticə) | STATUS |
| :--- | :--- | :--- | :--- | :---: |
| **CL-08** | Düymələrə sürətli klikləmə | Alt menyudakı düymələrə çox sürətli kliklədikdə tətbiq donmamalıdır. | Düymələrə sürətli kliklədə tətbiq donmur, keçidlər icra olunur. | **🔴 PASS** |
| **CL-09** | Boş səhifələrin idarə edilməsi | Hələ məlumat daxil edilməyən səhifələrdə istifadəçiyə vizual placeholder/göstərici çıxmalıdır. | “Tasks” səhifəsində bildiriş mətni düzgün çıxır, lakin “grades” səhifəsi tamamilə boş ağ ekran çıxır. | **❌ FAIL** |
| **CL-10** | İnternet bağlantısının qəfil kəsilməsi | Tətbiqdə interneti söndürdükdə istifadəçiyə anlaşılan şəbəkə xətası (no internet connection) çıxmalıdır. | Tətbiq tam çökmür, lakin ekranda texniki kod xətası göstərir. | **❌ FAIL** |
| **CL-11** | Tətbiqi arxa fona atmaq | Tətbiqi qəfil bağlayıb (minimize) yenidən açdıqda mövcud məlumatlar itməməlidir. | Tətbiqi arxa fona atıb açdıqda səhifə sıfırlanmır. | **🔴 PASS** |
| **CL-12** | Telefon zəngi kəsintisi | Aktiv istifadə zamanı telefona zəng gəldikdə tətbiq çökməməlidir. | Zəng və bildiriş gəldikdə tətbiq arxa fonda stabil işləyir. | **🔴 PASS** |
| **CL-13** | Ekranı fırlatmaq | Telefonu yana (landscape) çevirdikdə elementlər ekrana uyğunlaşmalı və sabit qalmalıdır. | Ekran fırladıldıqda elementlər ekrana düzgün uyğunlaşır. | **🔴 PASS** |
