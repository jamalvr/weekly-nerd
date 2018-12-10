# Artikel 2: CSS naming conventions

## Intro

Tijdens het eindproject voor de minor webdevelopment, hebben wij er met onze opdracht voor gekozen om in een team te gaan werken. Omdat weinig mensen daadwerkelijk ervaring hadden met het ontwikkelen van een website in teams, was het vrij lastig om dit op de juiste manier te coördineren. Iedereen had zijn eigen stijl en daarin zijn eigen niveau van CSS. Hierdoor ontstonden er veel fouten en veel extra herschrijfwerk voor sommige. Dit komt denk ik vooral omdat er veel manieren zijn om ‘’netjes’’ CSS te gebruiken en er nog minder mensen zijn die echt begrijpen hoe CSS daadwerkelijk werkt.

## Onderhoudbaar voor iedereen

Het belangrijkste is misschien wel dat je CSS onderhoudbaar geschreven wordt. Je werkt vaak niet alleen in een project en je wilt niet constant CSS opnieuw moeten schrijven omdat elkaars CSS in de weg zit. Om dit op te lossen zijn er bijvoorbeeld verschillende ‘’namingconventions’’ (BEM, OOCSS & SMACSS). Dit zijn conventies om je CSS leesbaar te houden voor iedereen en logisch op te bouwen. Naast de ‘’namingconventions’’ zijn er verschillende algehele regels voor CSS die iedere front-ender moet leren.

## Verschillende manieren van CSS schrijven

Wanneer je samenwerkt in een team, heeft iedereen zijn eigen stijl van CSS gebruiken. Dit houdt in dat bijvoorbeeld verschillende type classes aangemaakt worden die qua logica veel van elkaar verschillen.

```
<div class="container">
	<div class="column">
		<h1>Titel</h1>
		<p>Tekst</p>
	</div>
	<div class="column">
		<h2>Titel<h2>
		<p>Tekst</p>
	</div>
</div>
<!-- Voorbeeld 1 -->

<!-- VS -->

<!-- Voorbeeld 2 -->
<div class="content-block-two-column">
	<article>
		<h1>Titel</h1>
		<p>Tekst</p>
	</article>
	<article>
		<h2>Titel</h2>
		<p>Tekst</p>
	</article>
</div>
```

In het bovenstaande voorbeeld zie je dat het eerste voorbeeld zichzelf opbouwt aan de hand van de verschillende classnames. Elk element heeft zijn eigen specifieke classname en krijgt zo de styling mee. Het tweede voorbeeld heeft daarentegen allesomvattende class op het parent-element. Alle elementen in dit parent-element krijgen alle styling mee van de ene class die op het patentelement staat. Beide gevallen werken prima, maar wordt onleesbaar en onduidelijk wanneer dit tegelijkertijd wordt toegepast in hetzelfde project.

### CSS ’’namingconventions’’

De verschillende CSS ‘’namingsconventions’’ kunnen er voor zorgen dat er door iedereen dezelfde soort leesbare code geschreven wordt. Bij de meeste ‘’namingconventions’’ wordt niet alleen bepaald wat voor naam je een class geeft, maar ook hoe je een element opbouwt. Op deze manier zorg je er voor dat iedereen dezelfde soort code hanteert. Zoals eerder kort benoemd, zijn de meest gebruikte ‘’namingconventions’’: BEM, OOCSS & SMACSS.

#### BEM

Met Block Element Modifier (BEM) krijgt elk element basisstyling mee. Vervolgens krijgen aanpassingen of variaties op het blok dezelfde class naam plus een of twee toevoegingen. De eerste toevoeging geeft vaak aan wat voor type object het is. De tweede toevoeging geeft aan wat voor stijl er aan toegevoegd wordt.

```
/* --- BEM --- */
/* Block component */
.btn {}

/* Element that depends upon the block */
.btn__price {}

/* Modifier that changes the style of the block */
.btn--orange {}
.btn--big {}
```

#### OOCSS

Oftewel object oriented CSS. Hier is het vooral belangrijk dat je structuur en design van elkaar scheid. Het is belangrijk dat je zo veel mogelijk onderdelen hergebruikt (DRY: don’t repeat yourself). De basismodule krijgt al zijn eigen styling mee en wordt vervolgens aangepast met een ‘’inner’’ styling, waardoor er een variatie ontstaat uit de basismodule. Op deze manier schrijf je alleen code voor nieuwe element/aanpassingen.

```
/* --- OOCSS --- */
/* Talk Module */
.talk { base styling }

/* Part of Module */
.inner { added styling }

/* Variation of part inside Module */
.talk .inner { }
```

#### SMACSS

Met Scalable and Modular Architecture for CSS (SMACCS) Verdeel je al je elementen in verschillende categorieën. Omdat je alles opbouwt in verschillende categorieën, forceert het nog een keer zo objectief mogelijk naar een design te kijken. Alle elementen moet je uit elkaar kunnen trekken en die in de juiste categorieën plaatsen. Over het algemeen wordt er een nieuwe stylesheet per categorie gemaakt. Op deze manier vindt je makkelijker code die je wilt toevoegen of aanpassen.

Denk met categorieën aan bijvoorbeeld:

-   Basislayout
-   State van het element
-   Thema layout

```
/* --- SMACCS --- */
/* Example Module */
.btn { }

/* Modifier of the btn class */
.btn-primary { }

/* Btn Module with State */
.btn.is-collapsed { }
```

## Wat je moet doen

Uiteindelijk is het enige wat je moet doen: goed communiceren met je team en afspraken maken over hoe jullie de CSS gaan opbouwen. De genoemde “namingconventions” zijn voorbeelden waar je eventueel verder in zou kunnen verdiepen als het je aanspreekt. Je hoeft ze niet letterlijk te nemen, het zijn vooral guidelines om er voor te zorgen dat je leesbare, herbruikbare en voornamelijk onderhoudbaar code schrijft
