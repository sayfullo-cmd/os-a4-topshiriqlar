# Operatsion tizimlar — 4-topshiriq

**Mavzu:** Erkin mavzu (Operatsion tizimlar faniga oid C dasturi)
**Guruhlar:** SRM001-3, SRM002-2, SRM003-2
**O'qituvchi:** Bekimmetova Durdona

---

## 📌 Topshiriq

Operatsion tizimlar mavzularidan birini tanlab, **C tilida** ishlaydigan dastur yozing.

Mavzu namunalari:
- Jarayonlar: `fork()`, `exec()`, `wait()` — mini shell
- Operatsion tizim qurish
- Fayl tizimi: katalogni rekursiv aylanish, fayl nusxalash utilitasi
- Game yokida robototexnika loyihasi

O'zingiz boshqa mavzu taklif qilishingiz mumkin.

---

##  1-qadam: Loyihangizni o'z GitHub'ingizga yuklang

Loyiha reposida quyidagilar bo'lishi shart:
- `.c` fayllar (kod)
- `README.md` — F.I.Sh, guruh, mavzu, qisqa tavsif, qanday ishga tushiriladi
- `Makefile` yoki kompilyatsiya buyrug'i (masalan: `gcc main.c -o main -pthread`)

```bash
cd ~/mening-loyiham
git init
git add .
git commit -m "4-topshiriq: <mavzu>"
gh repo create os-a4-<familiya> --public --source=. --push
```

---

##  2-qadam: Shu repodagi jadvalga o'zingizni qo'shing

**1. Fork va clone**

Ushbu sahifada yuqori o'ngdagi **Fork** tugmasini bosing, so'ng:

```bash
git clone https://github.com/<USERNAME>/os-a4-topshiriqlar.git
cd os-a4-topshiriqlar
git remote add upstream https://github.com/Bekimmetova-classroom/os-a4-topshiriqlar.git
```

**2. Branch oching va jadval OXIRIGA qator qo'shing**

```bash
git checkout -b <guruh>-<familiya>
```

`README.md` ni oching, eng oxirgi qatordan keyin yozing:

```
| 1 | Familiya Ism | SRM002-2 | Mavzu | https://github.com/<USERNAME>/os-a4-<familiya> |
```

```bash
git add README.md
git commit -m "SRM002-2 Familiya Ism qo'shildi"
git push origin <guruh>-<familiya>
```

**3. Pull Request oching**

GitHub'da o'z fork'ingizga kiring → **Compare & pull request**.
Sarlavha: `SRM002-2 Familiya Ism`

---

##  3-qadam: Merge conflict chiqsa

Agar PR'da **"This branch has conflicts"** yozuvi chiqsa — demak sizdan oldin boshqa talaba qo'shilgan. Uni o'zingiz hal qilasiz:

```bash
git fetch upstream
git merge upstream/main
```

`README.md` da shunday belgilar paydo bo'ladi:

```
<<<<<<< HEAD
| 1 | Sizning qatoringiz |
=======
| 1 | Boshqa talabaning qatori |
>>>>>>> upstream/main
```

Nima qilish kerak:
1. `<<<<<<<`, `=======`, `>>>>>>>` qatorlarini o'chiring
2. **IKKALA qatorni ham qoldiring** — avval `main`dagisi, keyin sizniki
3. O'z raqamingizni to'g'rilang

```bash
git add README.md
git commit -m "Merge conflict hal qilindi"
git push origin <guruh>-<familiya>
```

PR avtomatik yangilanadi.

---

##  Qoidalar

- Boshqa talabaning qatorini **o'chirmang va o'zgartirmang** — bunday PR qaytariladi
- Bitta talaba — bitta PR
- Loyiha reposi **public** bo'lishi kerak
- Deadline'dan keyin kelgan PR'lar baholanmaydi
- Conflict'ni o'zingiz hal qilish — topshiriqning bir qismi

---

##  Baholash

| Mezon | Ball |
|-------|------|
| Dastur ishlaydi va mavzuga mos 
| Kod sifati va izohlar
| Loyiha README va Makefile 
| To'g'ri PR va conflict'ni hal qilish 
| Himoya (savollarga javob)

---

##  Topshirganlar ro'yxati

| # | F.I.Sh | Guruh | Mavzu | Repo |
|---|--------|-------|-------|------|
| 0 | Bekimmetova Durdona | O'qituvchi | Namuna | https://github.com/Bekimmetova |
| 1 | Xurramov Behruz | SRM002-2 | UzKey | https://github.com/BehruzXurramov/UzKey |
| 2 | Amirqulov Bahromjon | SRM002-2 | Mini Shell (Sodda buyruqlar interpretatori) | https://github.com/AmirqulovBaxromjon/os-a4-amirqulov |
| 4 | Homidov Abdukamol | SRM002-2 | TURBO JANG! — 3D poyga va parkovka o'yini | https://github.com/Abdukamol0870/os-a4-homidov |
| 5 | Ravshanov Rustamjon | SRM002-2 | Ilon arenasi (o'yin) | https://github.com/Rustam0614/os-a4-ravshanov |
| 6 | Sayfullo Avazbekov | SRM003-2 | AvtoWash — C tilida buyurtma va vaqtlarni boshqarish tizimi | https://github.com/sayfullo-cmd/os-a4-Avazbekov |
