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
<document>
    <titre>L’Adieu</titre>
    <poeme>
        <vers rime="A" num="1">J’ai cueilli ce brin de bruyère</vers>
        <vers rime="B" num="2">L’automne est morte souviens-t’en </vers>
        <vers rime="A" num="3">Nous ne nous verrons plus sur terre</vers>
        <vers rime="A" num="4">Odeur du temps brin de bruyère </vers>
        <vers rime="B" num="5">Et souviens-toi que je t’attends</vers>
    </poeme>
    <numeroPage num="70"/>
</document>
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
