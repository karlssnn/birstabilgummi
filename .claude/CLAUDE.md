# Arbetsregler för Birsta Bilgummis hemsida

## Visa alltid en förhandsvisning innan något förs in i main
`main` är den publicerade hemsidan. Innan en ändring förs in i `main` (merge av pull request eller push direkt):

1. Visa ändringen för användaren som en förhandsvisning, helst en klickbar privat förhandsvisning på claude.ai. Skärmdumpar av de berörda delarna på dator och mobil går också bra.
2. Vänta på att användaren säger ok till just den ändringen.

I förhandsvisningen ska `config.js` bytas mot en version som inte skickar något. Bokningar, beställningar och förfrågningar får inte nå det riktiga bokningsarket eller mejlen. Visa också tydligt att det är en förhandsvisning.

## Chefen ändrar själv via admin.html
Admin-sidan (`admin.html`) sparar texter och bilder direkt till `main` via ett separat Apps Script (commits heter "Ändrat via admin-sidan: …"). Priser, öppettider, gult meddelande och nyhetsrutan (`data-info`) sparas i stället i Info-kalkylarket. Hämta därför alltid `origin/main` och merga in den i din gren innan du för in något i `main`, och skriv aldrig över chefens ändringar.

## Språk
Användaren skriver på svenska. Svara på enkel svenska utan teknisk jargong.
