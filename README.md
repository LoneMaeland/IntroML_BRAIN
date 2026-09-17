# Kom i gang

Denne guiden hjelper deg å sette opp alt du trenger for å kjøre notebooken `Introduksjon_til_maskinlaering.ipynb` i VS Code. Du trenger bare å gjøre dette **én gang**.

## 1. Installer Python

1. Last ned Python fra [python.org/downloads](https://www.python.org/downloads/) (versjon 3.10 eller nyere).
2. Kjør installasjonsprogrammet.
   - **Viktig (Windows):** huk av for **"Add python.exe to PATH"** nederst i installasjonsvinduet, før du trykker "Install Now".
3. Sjekk at installasjonen fungerte. Åpne en terminal (se steg 3 under for hvordan) og skriv:
   ```
   python --version
   ```
   Du bør få opp noe sånt som `Python 3.12.x`.

## 2. Installer VS Code og utvidelser

1. Last ned og installer VS Code fra [code.visualstudio.com](https://code.visualstudio.com/).
2. Åpne VS Code, gå til utvidelser-fanen til venstre (firkantet ikon), og installer disse to (begge fra Microsoft):
   - **Python**
   - **Jupyter**

## 3. Åpne prosjektmappen i VS Code

1. Åpne VS Code.
2. Velg **File → Open Folder…** og velg mappen som inneholder `Introduksjon_til_maskinlaering.ipynb`, `cancer.csv`, `energy.csv` og `pokemon.csv`.
3. Åpne et terminalvindu inne i VS Code: **Terminal → New Terminal** (eller `Ctrl + ø`). Denne terminalen åpnes automatisk i riktig mappe.

## 4. Lag et eget miljø (anbefalt)

Dette gir deg et rent, isolert sted for pakkene til dette prosjektet, slik at de ikke kolliderer med annet du har installert.

I terminalen du åpnet i steg 3, kjør:

**Windows:**
```
python -m venv .venv
.venv\Scripts\activate
```

**Mac/Linux:**
```
python3 -m venv .venv
source .venv/bin/activate
```

Når miljøet er aktivert, skal du se `(.venv)` helt til venstre i terminal-linjen.

## 5. Installer pakkene notebooken trenger

Fortsatt i samme terminal:

```
pip install -r requirements.txt
```

Dette installerer `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn` og `ipykernel` — alt notebooken bruker.

## 6. Åpne og kjør notebooken

1. Klikk på `Introduksjon_til_maskinlaering.ipynb` i filutforskeren til venstre i VS Code.
2. Oppe til høyre i notebooken står det **"Select Kernel"**. Klikk der, velg **Python Environments**, og velg miljøet som heter noe sånt som `.venv` (det du nettopp lagde).
   - Hvis du ikke ser `.venv` med én gang, prøv å lukke og åpne notebook-fanen på nytt.
3. Trykk **Run All** øverst i notebooken (eller `Shift + Enter` celle for celle) for å kjøre alt.

## Feilsøking

- **"python" blir ikke gjenkjent i terminalen:** Python er trolig ikke lagt til i PATH. Installer Python på nytt og husk å huke av "Add to PATH".
- **Feilmelding om manglende pakke (f.eks. "No module named sklearn"):** Sjekk at riktig kernel er valgt (steg 6.2), og at du kjørte `pip install -r requirements.txt` mens `.venv` var aktivert.
- **Notebooken finner ikke CSV-filene:** Sjekk at `cancer.csv`, `energy.csv` og `pokemon.csv` ligger i samme mappe som `.ipynb`-filen.
- **Notebooken viser gammelt innhold etter en oppdatering:** Lukk fanen for notebooken i VS Code og åpne den på nytt (eller høyreklikk fanen → "Revert File"), slik at VS Code laster inn den nyeste versjonen fra disk.
