# Guida: Creare PR per il Repository di Giulio

Sei contributor, quindi puoi pushare direttamente un branch e creare una PR.

## Passaggi

### 1. Clona il repository

```bash
git clone https://github.com/GiulioTriggiani/STIX-2.1-Generator.git
cd STIX-2.1-Generator
```

### 2. Crea un nuovo branch

```bash
git checkout -b feature/ti-mindmap-hub-integration
```

### 3. Aggiungi i nuovi file

Copia i file da questo pacchetto nella directory del repo:

```bash
# Dalla cartella giulio-pr di questo pacchetto
cp README.md /path/to/STIX-2.1-Generator/
cp LICENSE /path/to/STIX-2.1-Generator/
cp CITATION.cff /path/to/STIX-2.1-Generator/
cp .gitignore /path/to/STIX-2.1-Generator/
cp requirements.txt /path/to/STIX-2.1-Generator/
```

### 4. (Opzionale) Riorganizza la struttura

Se vuoi anche riorganizzare i file:

```bash
cd STIX-2.1-Generator

# Crea directories
mkdir -p thesis notebooks results/standard results/graph

# Sposta files
mv Tesi_Triggiani_Giulio.pdf thesis/
mv GenAI_STIX_2_1_Generator_V13.ipynb notebooks/
mv Evaluation_GenAI_STIX_2_1_Generator_V9_Chart.ipynb notebooks/
mv Graph_Evaluation_GenAI_STIX_2_1_Generator_V6.ipynb notebooks/
mv Standard_Evaluation_Results/* results/standard/ 2>/dev/null
mv Graph_Evaluation_Results/* results/graph/ 2>/dev/null
rmdir Standard_Evaluation_Results Graph_Evaluation_Results 2>/dev/null
```

### 5. Commit e Push

```bash
git add .
git commit -m "feat: Integrate with TI Mindmap HUB research initiative

- Add MIT LICENSE
- Add CITATION.cff for academic citations
- Add requirements.txt with dependencies
- Update README with TI Mindmap HUB integration details
- Add .gitignore for Python/Jupyter
- (Optional) Reorganize repository structure"

git push origin feature/ti-mindmap-hub-integration
```

### 6. Crea la Pull Request

1. Vai su https://github.com/GiulioTriggiani/STIX-2.1-Generator
2. Vedrai un banner "Compare & pull request" - clicca
3. Compila la PR:

**Title:**
```
feat: Integrate with TI Mindmap HUB research initiative
```

**Description:**
```markdown
## Summary

This PR integrates the STIX 2.1 Generator with the TI Mindmap HUB research initiative, adding proper documentation, licensing, and academic citation support.

## Changes

### New Files
- `LICENSE` - MIT License for open source distribution
- `CITATION.cff` - Academic citation metadata (GitHub auto-recognizes this)
- `requirements.txt` - Python dependencies
- `.gitignore` - Standard Python/Jupyter ignores

### Updated Files
- `README.md` - Complete rewrite with:
  - TI Mindmap HUB integration details
  - Academic context (thesis, supervisor)
  - Methodology overview
  - Results summary
  - Citation information
  - Proper badges and links

### Optional: Repository Reorganization
- `thesis/` - Contains the thesis PDF
- `notebooks/` - Contains Jupyter notebooks
- `results/` - Contains evaluation results

## Related

- TI Mindmap HUB Platform: https://ti-mindmap-hub.com
- Research Repository: https://github.com/TI-Mindmap-HUB-Org/ti-mindmap-hub-research

## Checklist

- [ ] README accurately reflects the project
- [ ] LICENSE is appropriate (MIT)
- [ ] CITATION.cff has correct information
- [ ] All links work correctly

cc @GiulioTriggiani - Please review and let me know if any changes are needed!
```

4. Click "Create Pull Request"

---

## Note Importanti

### Personalizzazioni da fare PRIMA del commit

Nel `README.md`:
- Riga 24: Sostituisci "University Name" con il nome dell'università di Giulio

Nel `CITATION.cff`:
- Riga 10: Aggiungi ORCID di Giulio se disponibile
- Riga 26: Aggiorna `date-released` se necessario

### Se Giulio ha già una LICENSE

Verifica prima se esiste già un file LICENSE nel repo. In caso, discuti con lui quale usare.

### Alternative: Push Diretto

Se hai permessi di push su main (non solo contributor), potresti fare:

```bash
git checkout main
# ... applica modifiche ...
git commit -m "feat: Integrate with TI Mindmap HUB"
git push origin main
```

Ma la PR è preferibile per dare a Giulio visibilità sulle modifiche.
