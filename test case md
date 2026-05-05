# QA Test Hesabatı: Application Management System

Bu layihədə tətbiqin əsas funksionallıqları (Müraciət yaradılması, Tarixçə, PDF yükləmə və Silmə) həm istifadəçi interfeysi (UI), həm də verilənlər bazası (Database) səviyyəsində test edilmişdir.

## Test Case-lərin İcrası

| № | Prosesin təsviri | Gözlənilən nəticə | Faktiki nəticə | Database-in yoxlanılması |
|:---|:---|:---|:---|:---|
| 1 | *New Application* düyməsinin sıxılması. | Yeni müraciət forması (ad, soyad, sənəd yükləmə sahələri) ekranda görünməlidir. | Form bütün elementləri ilə birlikdə açıldı. | Bu mərhələdə bazada heç bir yeni sətir yaradılmamalıdır. |
| 2 | Açılmış formada məlumatların daxil edilməsi və *Approve for payments* düyməsinə sıxılması. | Sistem müraciəti qəbul etməli, dashboard-da yeni kart yaratmalı və status pending göstərilməlidir. | Dashboard-da "My Passport" müraciəti yarandı. Status pending olaraq göründü. | select * from applications where email = 'user@example.com'; sorğusu ilə bazada yeni sətir tapıldı. |
| 3 | *History* səhifəsinin açılması. | Dashboard-da yaradılan müraciətlər siyahıda görünməlidir. | Form bütün elementləri ilə açıldı. | select * from applications where email = 'user@example.com'; məlumatlar bazadakı ilə eynidir. |
| 4 | *PDF* düyməsinin sıxılması. | Müraciət məlumatlarını əks etdirən PDF sənədi uğurla yüklənməlidir. | PDF uğurla yükləndi. | Bu mərhələdə bazada heç bir yeni sətir yaradılmamalıdır. |
| 5 | *Delete* düyməsinin sıxılması. | Müraciət application history bölməsindən silinməlidir. | Form history bölməsindən silindi. | select * from applications where email = 'user@example.com'; sorğusunda 1 sətir bazadan silindi. |

## İstifadə olunan Texnologiyalar
- *Frontend Testing:* Manuel UI Testləri
- *Database Testing:* Supabase (PostgreSQL)
- *Sənədləşmə:* Markdown

## Nəticə
Aparılan testlər nəticəsində tətbiqin müraciət yaratma və idarəetmə funksiyalarının həm frontend, həm də backend tərəfdə stabil işlədiyi təsdiq edilmişdir.
