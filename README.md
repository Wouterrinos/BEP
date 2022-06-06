# BEP
Bachelor Eindproject Neerslag

Dit is de README voor de code van het Bachelor eindproject van Wouter van Rijkom (4484649).

### Intro
Het onderzoek voor het verkrijgen van de resultaten is met Python in Jupyterlab gedaan. De gegevens die gebruikt zijn zijn in het Netcdf4 format wat een soort multidimentionale matrix/tabel is (https://www.earthdatascience.org/courses/use-data-open-source-python/hierarchical-data-formats-hdf/intro-to-climate-data/). Om dit te openen en bewerken is er een extra pakket nodig om met Python hier mee te kunnen werken. Xarray (https://xarray-contrib.github.io/xarray-tutorial/oceanhackweek-2020/xarray-oceanhackweek20.html) is wat er gebruik is voor dit onderzoek. Dit zorgt ervoor dat er losse tabellen met neerslag gegevens voor iedere lengte en breedtegraad bekeken kunnen worden. Deze tabellen zijn in een gebruikelijk format (Numpy) en kunnen dan ook even eenvoudig gemanipuleert worden.

De data is makkelijk te downloaden van de Earthdata website. Het zijn namelijk allemaal losse bestanden, een voor iedere dag, dus om alles van de hele TRMM missie (slechts 15GB, maar meer dan 8000 bestanden) te downloaden zal een script gebruikt moeten worden dat het automatiseert. De instructie staan er op deze website direct bij na selectie van de data.

### Korte beschrijving code
De Singlecell code is voor het laten zien en te testen hoe de code gaat werken voor alle cellen samen en maakt daarom alle berekeningen voor een enkele cel. Alle data is hier nog steeds voor nodig, maar er word na aanvang enkel gebruik gemaakt van een enkele random cel. Iedere keer dat de code opnieuw loopt word er een nieuwe cel gekozen.

De Multiplecell doet dus hetzelfde (top 25 bijhouden voor blokken van 5 jaar, groepeer plek 1, 5 en 25 van alle blokken bij elkaar en maak een trendlijn), maar voor de hele grid van 576.000 cellen. Deze helling in mm/dag/jaar kan geplot worden door het op te slaan als netcdf4 en in Panoply te openen. Voor dit onderzoek was het echter vooral nodig om te kijken naar het verschil in procentuele stijging tussen de herhaaltijden. Dit word gedaan door de helling te delen door de begin hoogt bij het eerst jaar en deze voor de verschillende herhaaltijden van erkaar af te trekken. Deze kunnen ook in Panoply geplot worden nadat er een netcdf4 bestand van is gemaakt.
