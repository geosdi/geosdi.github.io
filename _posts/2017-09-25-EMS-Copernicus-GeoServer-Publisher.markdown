---
layout: post
title: Copernicus EMS Open Data GeoServer Publisher
date: '2017-09-25 09:00'
categories: Copernicus Features
tags: 'opendata,copernicus,ems'
image: >-
  /assets/article_images/2017-09-25-EMS-Copernicus-GeoServer-Publisher/satellite-4.jpg
image2: >-
  /assets/article_images/2017-09-25-EMS-Copernicus-GeoServer-Publisher/satellite-4.jpg
published: true
---

>Il servizio di gestione delle emergenze di Copernicus (EMS) espone un portale opendata dove è possibile accedere liberamente ai dati relativi a disastri naturali ed piu in generale a tutte le crisi umanitarie. Copernicus viene attivato da utenti autorizzati in base al rischio e l'impatto sulla popolazione mondiale.

All'interno del laboratorio geoSDI del CNR IMAA supportiamo progetti e programmi Copernicus, in questo articolo vi presentiamo una semplice soluzione software (open) in grado di automatizzare il processo di download e pubblicazione su gateway GeoServer delle attivazioni EMS Copernicus.

Le mappe prodotte dal sistema di Gestione delle Emergenze di Copernicus si suddividono in tre tipi principali:

- Mappe di Riferimento (**Reference maps**) : contengono dati che consentono velocemente di avere una **conoscenza** aggiornata sul territorio; vengono prodotte utilizzando dati acquisiti disponibili il più possibile vicini all'evento.

- Mappe di delineazione (**Delineation maps**) : contengono dati utili a fornire una valutazione dell'estensione dell'evento (e della sua evoluzione se richiesto). Le mappe di delineazione derivano dalle immagini post-disastro satellitari. Esse variano a seconda del tipo di catastrofe e delineamento delle aree colpite dal disastro.

- Mappe di Classificazione (**Grading maps**) : contengono dati utili a fornire una valutazione del **grado di danno**. Le mappe di classificazione sono derivate dalle immagini satellitari post-evento, comprendono i livelli di dimensione, grandezza o danno specifici per ciascun tipo di catastrofe. Possono anche fornire informazioni pertinenti e aggiornate specifiche per la popolazione e le risorse interessate, ad esempio insediamenti, reti di trasporto, industria e utilities.

Nel portale [EMS](http://emergency.copernicus.eu/) per ogni attivazione è possibile accedere ad una url del tipo :

[http://emergency.copernicus.eu/mapping/list-of-components/EMSR238](http://emergency.copernicus.eu/mapping/list-of-components/EMSR238)

![Schermata 2017-09-24 alle 17.28.06.png]({{site.baseurl}}/_posts/Schermata 2017-09-24 alle 17.28.06.png)


**EMSR238** è l'id che viene generato dal sistema Copernicus su richiesta, come si vede nell'immagine precedente) della Protezione Civile Nazionale per l'evento che ha colpito Livorno e Rosignano (Toscana - ITALIA) lo scorso 9 settembre 2017.

Come è possibile vedere accedendo all'url dell'evento, è possibile accedere ai dati relativi alle mappe di delineazione e classificazione.

![Schermata 2017-09-24 alle 17.39.48.png]({{site.baseurl}}/_posts/Schermata 2017-09-24 alle 17.39.48.png)

La repo **copernicus-ems-geosdi-publisher** contiene una semplice applicazione SpringBoot realizzata per automatizzare il processo di download dei dati da EMS e la publicazione su GeoServer dei file scaricati.

L'applicazione è concepita per essere usata da riga di comando e prende come parametro di input una lista di codici identificativi **EMSRXXXX**.

> java -jar copernicus-ems-geosdi-publisher.jar EMSR238,EMSR242
















