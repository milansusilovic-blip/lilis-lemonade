# Lili's Lemonade – uputstvo za objavu na Google Play

**Vlasnik i izdavač:** Milan Šušilović (lični Google Play nalog)
**Kontakt:** milan.susilovic@gmail.com
**Oznaka aplikacije (package name):** `com.milansusilovic.lilislemonade`
Oznaka se posle prve objave više ne može menjati.

Ovaj folder je gotov Android projekat. Aplikaciju (.aab fajl za Play Store) gradi GitHub besplatno, u oblaku. Na računar ne moraš ništa da instaliraš.

---

## Pregled celog puta

| # | Korak | Ko radi | Status |
|---|---|---|---|
| 1 | Verifikacija Play Console naloga | Google | čeka se |
| 2 | GitHub repozitorijum `milansusilovic-blip/lilis-lemonade` | Claude | ✅ urađeno |
| 3 | GitHub gradi aplikaciju, Claude je potpisuje tvojim ključem | Claude | ✅ automatski |
| 4 | Stranica sa politikom privatnosti | Claude | ✅ urađeno |
| 5 | Kreiranje aplikacije u Play Console-u | Ti (+ Claude pomaže) | posle verifikacije |
| 6 | Zatvoreni test: **12 testera, 14 dana** | Ti | 14+ dana |
| 7 | Zahtev za produkciju, pa javna objava | Ti | Google pregleda oko 7 dana |

**Adresa politike privatnosti (za Play Console):**
https://github.com/milansusilovic-blip/lilis-lemonade/blob/main/docs/PRIVACY.md

**Fajl za Play Store:** `lilis-lemonade-1.0.0-build3.aab`. Dobio si ga od Claude-a, već je potpisan.

---

## Ključ za potpisivanje

U zip-u **lilis-lemonade-KLJUC** su:
- `lilis-lemonade-upload.jks`, tvoj ključ
- `KEYSTORE-PODACI.txt`, njegova lozinka

Ključ se **ne nalazi na GitHub-u**. GitHub pravi nepotpisan fajl, a Claude ga potpisuje. Za svaku buduću verziju igre pošalji Claude-u ovaj zip zajedno sa zahtevom, da potpiše novi .aab.

Sačuvaj zip na dva mesta, na primer na USB i u Google Drive.

---

## Korak 5 – Aplikacija u Play Console-u

### 6a. Kreiraj aplikaciju
**Home → Create app**:
- App name: `Lili's Lemonade`
- Default language: **English (United States) – en-US**
- App or game: **Game**
- Free or paid: **Free**
- čekiraj obe izjave i klikni **Create app**.

### 6b. App content (levo dole: Policy → App content)
Odgovori kako piše u `store/LISTING.md`:
- **Privacy policy:** https://github.com/milansusilovic-blip/lilis-lemonade/blob/main/docs/PRIVACY.md
- **Ads:** No
- **App access:** All functionality is available without special access
- **Content rating:** popuni upitnik i na sve odgovori **No**. Očekivan rejting je Everyone / PEGI 3.
- **Target audience:** savetujem **13+** za početak, jer je tako pregled lakši i brži. Uzrast ispod 13 možeš dodati kasnije.
- **Data safety:** No, ne skupljamo podatke
- **Government apps / Financial features / Health:** No

### 6c. Store listing (Grow users → Store presence → Main store listing)
- Prekopiraj **Short description** i **Full description** iz `store/LISTING.md`.
- **App icon:** `store/icon-512.png`
- **Feature graphic:** `store/feature-graphic-1024x500.png`
- **Phone screenshots:** svih 5 iz `store/screenshots/`
- **Category:** Game → Casual
- **Contact email:** milan.susilovic@gmail.com

---

## Korak 6 – Zatvoreni test (12 testera, 14 dana)

Kod ličnog naloga ovo je **obavezno** pre javne objave.

### 7a. Napravi listu testera
1. Skupi **najmanje 12 Gmail adresa**. Dodaj 15–20, za slučaj da neko odustane. To mogu biti porodica, prijatelji, radnici iz radnje, poznanici.
2. Svaki tester mora da ima **Android telefon**.
3. Play Console → **Testing → Closed testing → Create track** (ili koristi postojeći „Alpha").
4. **Testers → Create email list**: nazovi listu npr. „Lili testeri", nalepi adrese odvojene zarezom i sačuvaj.

### 7b. Pošalji prvu verziju
1. **Create new release.** Kad pita za **Play App Signing**, klikni **Continue** (prihvati).
2. Ubaci potpisan `.aab` fajl koji ti je poslao Claude.
3. Release notes: `First test version of Lili's Lemonade.`
4. **Next → Save → Send for review.** Prvi pregled traje od par sati do par dana.

### 7c. Pozovi testere
Kad Google odobri, u **Testers** nađi **link za pridruživanje** (Join on Android). Pošalji ga testerima, na primer porukom:

> Ćao! Testiram svoju igricu za Google Play. Molim te:
> 1) otvori ovaj link sa telefona na kom si prijavljen ovim Gmail-om: [LINK]
> 2) klikni „Become a tester", pa instaliraj igru
> 3) **ne briši je 14 dana** i otvori je bar par puta.
> Hvala! 🍋

### 7d. Pravila koja Google gleda
- Najmanje **12 testera** mora biti **prijavljeno bez prekida 14 dana**. Ako neko izađe iz testa, njegovi dani se ne računaju.
- Dobro je da testeri zaista igraju i da pošalju bar par komentara.
- Ako tokom testa pošalješ novu verziju, brojanje se ne prekida.

---

## Korak 7 – Javna objava

1. Posle 14 dana, na **Dashboard**-u se otvara **Apply for production**.
2. Popuni kratak upitnik: kako si našao testere, šta su rekli, šta si popravio. Odgovori iskreno i konkretno.
3. Kad Google odobri, otvori **Production → Create new release**, ubaci isti (ili noviji) .aab i izaberi zemlje, na primer United States i sve ostale.
4. **Send for review.** Posle odobrenja igra je javno na Play Store-u.

---

## Nova verzija igre (kasnije)

Napiši Claude-u šta da promeni u igri i pošalji mu zip **lilis-lemonade-KLJUC**. Claude menja igru na GitHub-u, GitHub sam gradi novu verziju, a Claude ti šalje potpisan `.aab`. Ti ga samo ubaciš u Play Console.

---

## Slike sa Gemini-ja

Kad napraviš slike (Lili, prolaznike, butik, ulicu, artikle), pošalji mi ih. Ubaciću ih u igru i napraviti nove screenshotove. Za igru su najbolje slike sa **providnom pozadinom (PNG)**, sa likom koji stoji i gleda malo odozgo, kao na onoj slici iz „Decorate" igre.
