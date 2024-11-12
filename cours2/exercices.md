## Exercice 1: interpréter une DTD

Que veut dire:

```
<!ELEMENT metadonnees (auteur,titre,soustitre*,detail+,date)>
<!ELEMENT poeme (titre,strophe*,vers+)>
<!ELEMENT strophe (vers+)>
<!ELEMENT vers (#PCDATA)>
```

```
<!ELEMENT poeme (strophe*)>
<!ATTLIST strophe type (quatrain|tercet|sizain) #REQUIRED>
```

## Exercice 2: générer et tester un schéma dans oXygen

1. À partir du poème *L'Adieu* encodé la semaine dernière, générer un schéma XML avec oXygen

```
<?xml version="1.0" encoding="UTF-8"?>
<racine>
    <metaDonnees>
        <sourceGallica> https://gallica.bnf.fr/ark:/12148/bpt6k1083760/f70.item</sourceGallica>
        <auteur>Guillaume Apollinaire</auteur>
        <titre>L’Adieu</titre>
    </metaDonnees>
    <textePoeme>
        <vers n="1" rime="A">J’ai cueilli ce brin de bruyère</vers>
        <vers n="2" rime="B">L’automne est morte souviens-t’en </vers>
        <vers n="3" rime="A">Nous ne nous verrons plus sur terre</vers>
        <vers n="4" rime="A">Odeur du temps brin de bruyère </vers>
        <vers n="5" rime="B">Et souviens-toi que je t’attends</vers>
    </textePoeme>
</racine>
```

2. Créer un nouveau document, lui associer ce schéma, y encoder le poème *Automne*

```
Dans le brouillard s’en vont un paysan cagneux
Et son boeuf lentement dans le brouillard d’automne
Qui cache les hameaux pauvres et vergogneux

Et s’en allant là-bas le paysan chantonne
Une chanson d’amour et d’infidélité
Qui parle d’une bague et d’un coeur que l’on brise

Oh! l’automne l’automne a fait mourir l’été
Dans le brouillard s’en vont deux silhouettes grises
```

3. Ajouter  des balises `<strophe>`
4. Enregistrer à nouveau le schéma; l'associer au document contenant le poème *L'Adieu*
5. Ouvrir le schéma et trouver la définition de l'élément `<poeme>`
Utiliser `<xs:choice>` à la place de `<xs:sequence>` et rajouter l'élément `<strophe>`
6. vérifier la validité des deux documents avec ce nouveau schéma
7. observer dans oXygen l'arbre du schéma (cliquer sur `Design`) 

## Exercice 3: utiliser un schéma: la TEI

Encoder avec les balises `<sp>`, `<speaker>` et `<l>` le texte suivant:

```
Don Diègue
Ô rage! ô désespoir! ô vieillesse ennemie!
```

## Exercice 4: les métadonnées

Encoder de façon simplifiée les métadonnées pour un document TEI dont les références seraient:

```
Édition numérique du Capitulaire de Théodulf
Dans le cadre du cours d'initiation à XML de l'EnC
D'après l'édition de Peter Brommer (MGH, Capitula episcoporum, I) 
```	

Éléments à utiliser au sein des trois éléments obligatoires du `<fileDesc>`: `<title>`, `<author>`, `<p>`, `<bibl>`
