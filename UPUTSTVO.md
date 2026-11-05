# Whizzbang Workshop – objava na Google Play

Igrica je na engleskom, radi bez interneta, nema reklame ni kupovine i ne skuplja podatke.
Oznaka aplikacije: `com.milansusilovic.whizzbangworkshop`

## Šta dobijaš

| Fajl | Šta je |
|---|---|
| `whizzbang-workshop-1.0.0-build6.aab` | Gotova, potpisana aplikacija. Ide direktno u Play Console. |
| `store/icon-512.png` | Ikona za prodavnicu |
| `store/feature-graphic-1024x500.png` | Baner (Feature graphic) |
| `store/screenshots/` | 5 slika ekrana za telefon (1080 × 1920) |
| `store/LISTING.md` | Svi tekstovi na engleskom i odgovori za „App content" |
| zip **whizzbang-workshop-KLJUC** | Tvoj ključ za potpisivanje i lozinke |

Ključ sačuvaj na dva mesta (USB i Google Drive). Bez njega ne mogu da potpišem nove verzije igre.

Politika privatnosti (ovu adresu upisuješ u Play Console):
https://github.com/milansusilovic-blip/lilis-lemonade/blob/whizzbang-workshop/docs/PRIVACY.md

## Koraci u Play Console-u

1. **Create app**
   - App name: `Whizzbang Workshop`
   - Default language: English (United States)
   - App or game: **Game**
   - Free or paid: **Free**
   - Štikliraj obe izjave i klikni **Create app**.
2. **App content** (meni levo, dole): odgovori kako piše u `store/LISTING.md`. Tu su privatnost, reklame, rejting, ciljna publika i Data safety.
3. **Main store listing**: prekopiraj tekstove iz `store/LISTING.md` i ubaci ikonu, baner i 5 slika ekrana.
4. **Testing → Closed testing**
   - napravi test i ubaci `.aab` fajl
   - dodaj email adrese testera; za lični nalog treba **12 testera tokom 14 dana**
   - pošalji na pregled
   - Kod prvog `.aab`-a Google pita za **Play App Signing**. Prihvati podrazumevano.
5. Posle 14 dana testa: **Production → Create release**, ubaci isti `.aab`, izaberi zemlje i pošalji na pregled.

Testeri: možeš da koristiš iste ljude kao za Lili's Lemonade. Isti tester može istovremeno da testira obe igrice.

## Nova verzija igre

Napiši mi šta da promenim i pošalji zip **whizzbang-workshop-KLJUC**. Ja menjam igru, GitHub gradi novu verziju, a ja ti šaljem potpisan `.aab` koji samo ubaciš u Play Console.

## Napomena o GitHub-u

Igra se trenutno gradi u tvom postojećem repozitorijumu `lilis-lemonade`, u posebnoj grani `whizzbang-workshop`. Lili's Lemonade nije diran. Ako želiš poseban repozitorijum samo za ovu igru, napravi prazan repozitorijum `whizzbang-workshop` na GitHub-u i javi mi, prebaciću sve.
