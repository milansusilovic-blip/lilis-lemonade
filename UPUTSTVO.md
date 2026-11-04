# Lili's Lemonade – uputstvo za objavu na Google Play

**Vlasnik i izdavač:** Milan Šušilović (lični Google Play nalog)
**Kontakt:** milan.susilovic@gmail.com
**Oznaka aplikacije (package name):** `com.milansusilovic.lilislemonade`
Oznaka se posle prve objave više ne može menjati.

Ovaj folder je gotov Android projekat. Aplikaciju (.aab fajl za Play Store) gradi GitHub besplatno, u oblaku. Na računar ne moraš ništa da instaliraš.

---

## Pregled celog puta

| # | Korak | Koliko traje |
|---|---|---|
| 1 | Verifikacija Play Console naloga | Čekaš Google (obično 1–3 dana) |
| 2 | GitHub nalog i repozitorijum | 10 min |
| 3 | Ključ u GitHub Secrets | 5 min |
| 4 | GitHub gradi aplikaciju (.aab) | 10 min |
| 5 | Stranica sa politikom privatnosti | 5 min |
| 6 | Kreiranje aplikacije u Play Console-u | 30–45 min |
| 7 | Zatvoreni test: **12 testera, 14 dana** | 14+ dana |
| 8 | Zahtev za produkciju, pa javna objava | Google pregleda oko 7 dana |

Dok čekaš verifikaciju (korak 1), uradi korake 2–5.

---

## Šta je u paketu

| Folder / fajl | Šta je |
|---|---|
| `www/` | Sama igra sa fontovima, radi bez interneta |
| `android/` | Android projekat (Capacitor 8, Android 16 / API 36, uspravni ekran, ikonice, početni ekran) |
| `.github/workflows/build-android.yml` | Recept po kom GitHub pravi potpisan .aab i .apk |
| `docs/privacy-policy.html` | Politika privatnosti na tvoje ime |
| `store/` | Ikona 512, baner 1024×500, 5 screenshotova i tekstovi (`LISTING.md`) |

Odvojeno, u zip-u **lilis-lemonade-KLJUC**, dobijaš:
- `lilis-lemonade-upload.jks`, tvoj ključ za potpisivanje
- `KEYSTORE-PODACI.txt`, lozinke za taj ključ

Sačuvaj oba fajla na dva mesta, na primer na USB i u Google Drive. **Nikad ih ne stavljaj na GitHub kao fajlove.** Ako ih izgubiš, ključ se može zameniti preko Google podrške, ali to traje.

---

## Korak 1 – Verifikacija naloga (u toku)

Google proverava tvoj identitet. Dok čekaš:
- Proveri da li ti je stigao email od Google Play Console-a. Nekad traže još neki dokument.
- U Play Console-u, pod **Account details**, proveri da su ime i adresa tačni.

Kod ličnog naloga Google ponekad traži i potvrdu da imaš **Android telefon**. Tada instaliraš aplikaciju *Play Console* na telefon i prijaviš se istim nalogom.

---

## Korak 2 – GitHub repozitorijum

1. Otvori https://github.com i napravi besplatan nalog. Najbolje je da ga otvoriš na isti Gmail.
2. Gore desno klikni **+ → New repository**:
   - Repository name: `lilis-lemonade`
   - **Public** (potrebno za besplatnu stranicu sa politikom privatnosti)
   - klikni **Create repository**.
3. Na stranici praznog repozitorijuma klikni link **uploading an existing file**.
4. Raspakuj `lilis-lemonade-app.zip` na računaru i prevuci **sav sadržaj foldera**, ne sam folder, u prozor na GitHub-u.
5. Dole klikni **Commit changes**.
6. Proveri da se u repozitorijumu vidi folder **`.github`**. Windows ponekad ne prevuče foldere koji počinju tačkom. Ako ga nema:
   - klikni karticu **Actions → set up a workflow yourself**
   - promeni ime fajla u `build-android.yml`
   - obriši sve u prozoru i zalepi sadržaj fajla `.github/workflows/build-android.yml` iz paketa (otvori ga u Notepad-u)
   - klikni **Commit changes**.

---

## Korak 3 – Ključ u GitHub „Secrets"

1. U repozitorijumu otvori **Settings** (gore desno) → levo **Secrets and variables → Actions**.
2. Klikni **New repository secret** i dodaj 4 secreta. Ime i vrednost prepiši tačno iz `KEYSTORE-PODACI.txt`:

| Name | Secret |
|---|---|
| `KEYSTORE_BASE64` | onaj dugački red teksta |
| `KEYSTORE_PASSWORD` | lozinka |
| `KEY_ALIAS` | `lilis-upload` |
| `KEY_PASSWORD` | ista lozinka |

---

## Korak 4 – GitHub gradi aplikaciju

1. Otvori karticu **Actions**. Ako pita, klikni **I understand my workflows, go ahead and enable them**.
2. Levo izaberi **Build Android (Play Store)**, pa desno klikni **Run workflow**.
3. Ostavi verziju `1.0.0` i klikni zeleno dugme **Run workflow**.
4. Sačekaj 5–10 minuta, dok se ne pojavi zelena kvačica ✅.
5. Klikni na taj run i skroluj dole do **Artifacts**. Preuzmi zip i raspakuj ga. U njemu su:
   - `app-release.aab`, fajl za Play Store
   - `app-release.apk`, fajl za probu na tvom telefonu

Ako dobiješ crveni ✗, klikni na run, pa na korak koji je crven. Iskopiraj tekst greške i pošalji ga meni.

**Proba na telefonu:** pošalji sebi `app-release.apk`, otvori ga na telefonu i dozvoli „instalaciju iz nepoznatih izvora".

---

## Korak 5 – Stranica sa politikom privatnosti

1. U repozitorijumu otvori **Settings → Pages**.
2. Pod **Build and deployment → Branch** izaberi `main` i folder `/docs`, pa klikni **Save**.
3. Posle 2–5 minuta stranica radi na adresi:
   `https://TVOJE-GITHUB-IME.github.io/lilis-lemonade/privacy-policy.html`
4. Otvori je u pregledaču da proveriš. Tu adresu ćeš upisati u Play Console.

---

## Korak 6 – Aplikacija u Play Console-u

### 6a. Kreiraj aplikaciju
**Home → Create app**:
- App name: `Lili's Lemonade`
- Default language: **English (United States) – en-US**
- App or game: **Game**
- Free or paid: **Free**
- čekiraj obe izjave i klikni **Create app**.

### 6b. App content (levo dole: Policy → App content)
Odgovori kako piše u `store/LISTING.md`:
- **Privacy policy:** adresa iz koraka 5
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

## Korak 7 – Zatvoreni test (12 testera, 14 dana)

Kod ličnog naloga ovo je **obavezno** pre javne objave.

### 7a. Napravi listu testera
1. Skupi **najmanje 12 Gmail adresa**. Dodaj 15–20, za slučaj da neko odustane. To mogu biti porodica, prijatelji, radnici iz radnje, poznanici.
2. Svaki tester mora da ima **Android telefon**.
3. Play Console → **Testing → Closed testing → Create track** (ili koristi postojeći „Alpha").
4. **Testers → Create email list**: nazovi listu npr. „Lili testeri", nalepi adrese odvojene zarezom i sačuvaj.

### 7b. Pošalji prvu verziju
1. **Create new release.** Kad pita za **Play App Signing**, klikni **Continue** (prihvati).
2. Ubaci `app-release.aab` iz koraka 4.
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

## Korak 8 – Javna objava

1. Posle 14 dana, na **Dashboard**-u se otvara **Apply for production**.
2. Popuni kratak upitnik: kako si našao testere, šta su rekli, šta si popravio. Odgovori iskreno i konkretno.
3. Kad Google odobri, otvori **Production → Create new release**, ubaci isti (ili noviji) .aab i izaberi zemlje, na primer United States i sve ostale.
4. **Send for review.** Posle odobrenja igra je javno na Play Store-u.

---

## Nova verzija igre (kasnije)

1. Zameni `www/index.html` na GitHub-u: klikni na fajl → olovka (Edit) ili **Upload files**.
2. **Actions → Run workflow** sa većom verzijom, npr. `1.0.1`. Broj builda raste sam.
3. Ubaci novi `.aab` u Play Console (u test ili u produkciju).

---

## Slike sa Gemini-ja

Kad napraviš slike (Lili, prolaznike, butik, ulicu, artikle), pošalji mi ih. Ubaciću ih u igru i napraviti nove screenshotove. Za igru su najbolje slike sa **providnom pozadinom (PNG)**, sa likom koji stoji i gleda malo odozgo, kao na onoj slici iz „Decorate" igre.
