# Birsta Bilgummi – hemsida

Det här är hela hemsidan. Alla filer ligger direkt i det här repot.

## Så publicerar du (tar 2 minuter)

1. Logga in på **github.com** med firmans konto.
2. Öppna repot **birstabilgummi**.
3. Tryck **Settings** (kugghjulet högst upp), sedan **Pages** i menyn till vänster.
4. Under *Build and deployment*:
   - **Source:** Deploy from a branch
   - **Branch:** `main` och mappen `/ (root)`
   - Tryck **Save**.
5. Vänta 1–2 minuter och ladda om sidan. Överst står adressen, *Your site is live at ...*

Sidan är nu publicerad. Under **Settings → Pages** finns även ett val för att ta ner sidan igen (*Unpublish site*).

> Repot måste vara **Public** för att gratis-Pages ska fungera. Här finns inga hemligheter, bara sidans egna filer.

## Ändra priser, däck och öppettider (utan GitHub)

Det görs i två Google-kalkylark. Ändringen syns på sidan så fort någon laddar om den.

**Däck-arket** har en rad per däck med kolumnerna *Märke, Dimension, Pris, Status, Typ*.

| Vill du... | Gör så här |
|---|---|
| Ändra ett pris | Ändra siffran i kolumnen *Pris* |
| Lägga till ett däck | Ny rad. Dimension skrivs t.ex. `205/55R16`, pris bara med siffror |
| Lägga till vinterdäck | Skriv **Vinter** i kolumnen *Typ* (annars räknas det som sommardäck) |
| Ta bort ett däck som är slut | Skriv **Slut** i *Status* |
| Visa ett däck som beställningsvara | Skriv **Beställning** i *Status*. Det visas då under *Beställ däck* |

**Info-arket** har kolumnerna *Nyckel* och *Värde*.

| Nyckel | Vad det styr |
|---|---|
| `banner` | Gul text högst upp på alla sidor, t.ex. "Stängt vecka 28". Tomt = ingen banner |
| `oppettider` | Öppettiderna längst ner på startsidan och på fälgsidan |
| `pris_hjulinstallning` | Priset på hjulinställning |
| `pris_dackbyte` | Priset på däckbyte |
| `nyhet_rubrik`, `nyhet_text` | Rubrik och text i nyhetsrutan som kommer upp när man går in på sidan. Skriv `-` i rubriken för att dölja rutan |
| `nyhet_lank`, `nyhet_lanktext` | Lägger till en knapp med länk i nyhetsrutan |

Tre regler så att inget går sönder: ändra aldrig rubrikraden eller kolumnernas ordning, skriv bara siffror i *Pris*, och behåll bokstaven R i dimensionen (`205/55R16`).

Det som är i arken är synligt för alla som kan sidan. Skriv därför inget där som inte är offentligt, t.ex. inköpspriser.

## Bokningar, beställningar och förfrågningar

När en kund bokar hjulinställning, beställer däck eller skickar en förfrågan sparas det i arket **Birsta Bilgummi: Bokningar och förfrågningar**, och ett mejl skickas. Bokade tider spärras automatiskt för nästa kund.

Vill du avboka en tid skriver du **Avbokad** i kolumnen *Status* på raden i fliken *Bokningar*. Då blir tiden ledig igen.

## Ändra texter, bilder eller utseende

1. Öppna repot på github.com och tryck på filen som ska ändras (t.ex. `tjanster.html`).
2. Eller: tryck **Add file → Upload files** och släpp in den nya filen med **samma namn**. Den ersätter den gamla.
3. Tryck **Commit changes**. Ändringen syns på sidan efter ungefär en minut.

## Filerna i repot

| Fil | Vad det är |
|---|---|
| `index.html` | Startsidan |
| `dack.html` | Däck: val av sommar/vinter, sök, prislista, beställning |
| `falgar.html` | Fälgar |
| `hjulinstallning.html` | Boka hjulinställning |
| `tjanster.html` | Övriga tjänster och förfrågan |
| `integritet.html` | Integritet och kakor |
| `404.html` | Sidan som visas om länken inte finns |
| `config.js` | Adressen till tjänsten som kopplar sidan till kalkylarken |
| `favicon.svg`, `favicon.png` | Ikonen i webbläsarfliken |
| `robots.txt` | Låter sökmotorer läsa sidan |

## Flytta tjänsten till firmans Google-konto

Kalkylarken och tjänsten (Google Apps Script) ligger just nu i det Google-konto där de skapades. För att firman ska äga dem:

1. Skapa de två arken (*Däck* och *Info*) i firmans Google-konto med samma kolumner.
2. Lägg tjänstens kod i ett nytt Apps Script-projekt i firmans konto, byt de två ark-ID:na och mejladressen längst upp i koden, kör `setup` och distribuera som webbapp med *Åtkomst: Alla*.
3. Byt adressen i filen `config.js` mot den nya webbappens adress.

## Egen domän (birstabilgummi.se) – gör detta sist

1. Gå till **Settings → Pages → Custom domain**, skriv in domänen och spara.
2. Ändra DNS-inställningarna hos den som sköter domänen enligt de värden GitHub visar där.
3. Säg inte upp den gamla hemsidetjänsten förrän den nya sidan fungerar på den riktiga adressen.

## Innan ni publicerar – kolla särskilt

- Att **öppettiderna** i Info-arket är rätta och skrivna som kunden ska läsa dem (t.ex. `Mån–fre 07:30–16:30`).
- Att texten på `integritet.html` stämmer med hur ni arbetar. Den säger bland annat att bokningar och förfrågningar sparas högst 12 månader, och då måste ni rensa arket med jämna mellanrum.
- Att ni får visa **Pirelli-nyheten**, och lägg gärna in en länk till testerna i Info-arket (`nyhet_lank`).
- Att priserna, dimensionerna och märkena i Däck-arket stämmer.
