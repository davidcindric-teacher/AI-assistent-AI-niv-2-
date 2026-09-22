# Bygg och utvärdera en AI-assistent

Statisk arbetsyta för projektet i gymnasiekursen **AI nivå 2**. Eleverna planerar, bygger instruktion till, testar och dokumenterar en egen AI-assistent.

## Syfte

Eleverna, som arbetar i par, utformar en AI-assistent som löser ett tydligt problem för en bestämd målgrupp. Webbplatsen hjälper dem att formulera instruktioner, samla faktaunderlag, dokumentera tester och exportera arbetet. Individuell loggbok och reflektion skrivs i elevens eget arbetsdokument, inte på webbplatsen. Projektet omfattar cirka åtta lektioner à 80 minuter.

## Webbplatsen har ingen egen AI-modell

Webbplatsen anropar inget AI-API och skickar ingen data någonstans. Eleverna använder ett **separat, av skolan godkänt AI-verktyg** (till exempel Claude eller ChatGPT) i en annan flik. De kopierar sin instruktion och sitt faktaunderlag dit och för tillbaka testresultaten till webbplatsen.

## Publicera på GitHub Pages

1. Skapa ett repository på GitHub och lägg filerna `index.html`, `styles.css`, `app.js` och `README.md` i rotmappen.
2. Gå till **Settings → Pages**.
3. Under **Build and deployment**, välj **Deploy from a branch**, branchen `main` och mappen `/ (root)`. Klicka på **Save**.
4. Efter någon minut finns sidan på `https://<användarnamn>.github.io/<repository>/`.

Filerna kan också öppnas direkt från en lokal mapp (dubbelklicka på `index.html`). Lokal test: kör `python3 -m http.server` i mappen och öppna `http://localhost:8000`.

## Lokal lagring

Allt eleven skriver autosparas i webbläsarens `localStorage` under namnet `ai2-assistent-arbetsyta-v1`. Det innebär att:

- arbetet finns kvar när sidan laddas om,
- arbetet finns **bara i just den webbläsaren på just den datorn** (och profilen),
- arbetet försvinner om webbläsarens data rensas eller om man byter dator eller webbläsare.

Sidhuvudet visar när senaste autosparning skedde och om det finns ändringar som inte exporterats.

## Så exporterar eleverna sitt arbete

- **Exportera arbete** (startsidan): laddar ner en JSON-fil som säkerhetskopia. **Importera arbete** läser in en sådan fil igen.
- **Exportera komplett arbetsrapport** (Inlämning): laddar ner en läsbar Markdown-rapport (.md) och en JSON-fil.
- Testprotokollet kan exporteras separat från Testlaboratoriet.

Eleverna ska exportera innan de byter webbläsare eller dator och lämna in filerna i Google Classroom.

## Återställa en tidigare version (för läraren)

- **Elevens arbete:** be eleven importera en äldre JSON-fil med **Importera arbete**. Be eleverna spara filer med datum, till exempel efter varje lektion. Google Classroom sparar tidigare inlämningar.
- **Webbplatsen:** om repositoryt ligger på GitHub kan du gå till **Commits**, välja en tidigare commit och återställa (`git revert <commit>`) eller checka ut den. Pages publicerar om automatiskt.

## Ingen API-nyckel i repositoryt

Webbplatsen behöver ingen API-nyckel, inloggning, databas eller server. **Lägg aldrig någon API-nyckel, något lösenord eller några personuppgifter i repositoryt.** Elever ska heller inte skriva riktiga personuppgifter i faktaunderlaget.

## Filer

| Fil | Innehåll |
| --- | --- |
| `index.html` | Sidans struktur och text |
| `styles.css` | Utseende (björk- och klorofylltema) |
| `app.js` | Formulär, autosparning, export och import |
| `README.md` | Den här filen |

Inga externa bibliotek, typsnitt, bilder eller analysverktyg används.
