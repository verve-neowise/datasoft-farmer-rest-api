# RestAPI Requirements

Siz Fermer xo`jalikining malumotlarini boshqarish uchun Rest Service yaratishingiz kerak.

---

> Barcha endpointlar, modellar va boshqa texnik nomlar mustaqil ravishda tuziladi (ohirda nomlash uchun maslahatlar berilgan)

>  Rest Service istalgan tilda va texnologiyada tuzlishi mumkin

> Ma`lumotlar Bazalari (Database) bolishi muhim emas, oddiy massiv yordamida yaratish ham mumkin. Agar database ishlatmoqchi bolsangiz, qisqa vaqt oluvchi SQLite yoki online Postgres database https://www.elephantsql.com/ 
ni tavsiya beramiz 

---

Rest API ning asosiy vazifalari fermalar va ekinlar ro`yhalarini boshqarish:

## Fermalar

Fermaning ma`lumotlari:

- unkal identifikator
- fermaning nomi
- fermaning egasi ismi sharifi
- manzili
- o`lchami (metr kvadtrat)
- yillik foydasi

Fermalar royhatini boshqarish funksionali

- Yangi ferma qo'shish
- Barcha fermalar ro`yhatini olish
- Bor fermani 'id' boyicha yangilash
- Bor fermani 'id' boyicha o`chirish

## Ekinlar

Ekin ma`lumotlari:

- unikal identifikator
- tegishli bolgan ferma identifikatori
- ekin nomi
- ekilgan maydon o`lchami (metr kvatrat)

Ekinlar royhatini boshqarish funksionali

- Mavjud ekinlar ro'yhatini olish
- Yangi ekin qoshish fermaga bog'langan ravishda (fermaning `id` orqali bog`lanadi)
- Mavjud ekinni `id` orqali o'zgaritish (ferma `id`-dan tashqari barcha malumotlar o`zgaradi)
- Mavjud ekinni `id` orqali o`chirish
- Ferma `id`-si orqali shu fermaga tegishli ekinlarni olish

---

## Baholash nizomi

1. Rest Service yuqoridagi talablarga binoan yaratilgan va ishlamoqda
2. API endpointlari ingiliz tilida aniq va koplik formasida yozilgan
3. Har bir operatsiya uchun mos method ishlatilgan (Malumot olish uchun `GET`, yaratish uchun `POST` h.k.)
4. Har bir operatsiya bajarilgandan so'ng client tomonga aniq bolgan formatda ma'lumot qaytyabdi

---

## Maslahatlar

1. Endpointlar nomlari koplik formasida yozing, chunki endpoint bitta ma'lumot bilan emas balki kop ma'lumot bilan ishlaydi. Masalan `/users`

2. Har bir operatsiya uchun maxsus http metod ishlating

- Malumot olish uchun `GET`
- Malumot yaratish uchun `POST`
- Ozgartirish uchun `PUT`
- O'chirish uchun `DELETE`

3. Har bir endpointning har birini funksionalini yaratigach tekshirib koring va keyingi vazifaga o'ting. Aks holda barchasini bittada tekshish uchun ancha vaqt ketishi mumkin

4. Endpointlarni tekshirishda VSCode Extension `Rest Client` yoki `Thunder`dan foydalaning

5. Kodni githubga yuklang