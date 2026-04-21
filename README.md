# Courses à deux

## Comment tester

### 1) Vérifier que le JavaScript est valide
```bash
node -e "const fs=require('fs');const s=fs.readFileSync('index.html','utf8');const js=s.split('<script>')[1].split('</script>')[0];new Function(js);console.log('JS OK')"
```

Résultat attendu : `JS OK`

### 2) Lancer l'app en local
```bash
python3 -m http.server 8000
```
Puis ouvrir : http://localhost:8000

### 3) Vérifications manuelles de la saisie
1. Cliquer sur `+`.
2. Vérifier que le bouton `Ajouter` est désactivé tant que le nom est vide.
3. Saisir un nom avec des espaces multiples (ex: `  lait   demi-écrémé  `) puis ajouter.
4. Vérifier que le nom est enregistré nettoyé (espaces normalisés).
5. Cliquer sur un raccourci quantité (`x2`, `500g`, etc.) et vérifier que le champ quantité se remplit.
6. Vérifier la suggestion automatique de noms (datalist) lors d'une nouvelle saisie.
7. Vérifier la touche Entrée :
   - dans le nom, elle passe à la quantité si quantité vide ;
   - sinon elle ajoute l'article.
