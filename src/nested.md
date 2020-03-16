# Bootstrap

## 1. Annidiare le colonne

Bootstrap permette di **annidare le colonne**, cioè di inserire una nuova griglia all'interno di un'altra griglia. Per farlo è sufficiente definire una riga (un div con **classe "row"**) all’interno di una colonna e quindi definire le colonne annidate all’interno di ciascuna riga.

Ogni riga annidata contiene a sua volta una griglia di 12 colonne che si possono riempire esattamente come quella della griglia di primo livello.

Per consultare la documentazione ufficiale di Bootstrap sulle **nested columns** o **colonne annidate** [cliccate qui](https://getbootstrap.com/docs/4.4/layout/grid/#nesting)

*Qui di seguito un esempio*

Un div di classe `container` all'interno del quale c'è un div di classe `row` all'interno del quale 2 div di classe `col-6` che hanno quindi una larghezza del 50% della viewport ciascuno.

All'interno di uno dei due div di classe `col-6` ho annidato 4 colonne di classe `col-3`. Per farlo è necessario inserire all'interno del div `col-6` un altro div di classe `row` ed all'interno di esso i div di classe colonna:

```html
<div class="container">
  <div class="row">
    <div class="col-6">
      <h2>colonna 1</h2>
      
      <!-- COLONNE ANNIDIATE -->
      <div class="row">
        <div class="col-3">colonna annidata 1</div>
        <div class="col-3">colonna annidata 2</div>
        <div class="col-3">colonna annidata 3</div>
        <div class="col-3">colonna annidata 4</div>
      </div>
      
    </div>
    <div class="col-6">
    
      <h2>colonna 2</h2>
    
    </div>
  </div>
</div>
```

La riga annidata come si può vedere contiene  a sua volta la griglia di 12 colonne

![colonne annidate](https://www.mrwebmaster.it/img/upl/guida_bootstrap/Figura09.jpg)

### Utilizzi pratici relativi all'annidamento

Le colonne annidate servono essenzialmente a due utilizzi:

1. Creare delle sidebar
2. Poter utilizzare i margini orizzontali



#### 1. Creiamo una sidebar

Come abbiamo già detto in classe per utilizzare il codice compilato di Bootstrap nel tuo progetto, è sufficiente scaricare ed includere nella pagina HTML alcuni file, tra cui un file CSS, ed alcuni file Javascript, scaricabili [qui](https://github.com/twbs/bootstrap/releases/download/v4.4.1/bootstrap-4.4.1-dist.zip)

È sempre consigliabile utilizzare la **versione più recente della libreria e mantenerla aggiornata** sui propri progetti. La versione più recente tra le release di progetto contiene anche tutti i miglioramenti e le correzioni disponibili fino ad oggi.

##### Oppure utilizzare lo starter template

In alternativa senza dover scaricare le librerie in locale possiamo utilizzare lo **starter template** presente sul sito ufficiale [Cliccando qui](https://getbootstrap.com/docs/4.4/getting-started/introduction/#starter-template) 

*Starter template*

```html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css">

    <title>Colonne annidate</title>
  </head>
  <body>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.4.1.slim.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js"></script>
  </body>
</html>
```



Salviamo il file nella root del sito chiamandolo **04-grid-layout-nested.html**

Sulla nostra root dovremmo avere i seguenti file:

- 01-starter-template.html
- 02-grid-layout.html
- 03-grid-layout-sample.html
- 04-grid-layout-nested.html



###### Creiamo le colonne

Supponiamo che la nostra sidebar dovrà essere larga un terzo della viewport quando la dimensione dello schermo è superiore o uguale ai 992px, cioè quando ci troviamo nella viewport **Large** o **Extra large**

|                     | Extra small <576px | Small ≥576px | Medium ≥768px | Large ≥992px | Extra large ≥1200px |
| ------------------- | ------------------ | ------------ | ------------- | ------------ | ------------------- |
| Max container width | None (auto)        | 540px        | 720px         | 960px        | 1140px              |
| Class prefix        | `.col-`            | `.col-sm-`   | `.col-md-`    | `.col-lg-`   | `.col-xl-`          |
| # of columns        | 12                 |              |               |              |                     |
| Gutter width        | 30px               |              |               |              |                     |
| Nestable            | Yes                |              |               |              |                     |
| Column ordering     | Yes                |              |               |              |                     |

Vi ricordo che le classi delle colonne indicano il numero delle colonne che dovreste utilizzare in base alle 12 possibili per riga. Quindi, se vogliamo avere tre colonne di uguale larghezza, possiamo usare la classe `.col-4`. che corrisponde appunto ad una larghezza di 4 colonne sulle 12 disponibile che è appunto di un terzo della larghezza della viewport.

I tre elementi di classe `.col-4`. saranno larghi rispettivamente 1/3 + 1/3 + 1/3 della viweport

```html
<div class="container">
       <div class="row">
           <div class="col-4">Colonna 1</div>
           <div class="col-4">Colonna 2</div>
           <div class="col-4">Sidebar</div>
       </div>
</div>
```
Abbiamo detto però che vogliamo che siano larghe 1/3 solo a determinate viewport (Large ed Extra Large), 

Quindi sfruttando i breakpoint della griglia di bootstrap che si basano su media query con larghezza minima e cioè che **si applicano a quel breakpoint e a tutti quelli sopra di esso** dovremmo aggiuingere il prefisso `-lg`, e scrivere il codice così:

```markdown
   <div class="container">
       <div class="row">
           <div class="col-lg-4">Colonna 1</div>
           <div class="col-lg-4">Colonna 2</div>
           <div class="col-lg-4">Sidebar</div>
       </div>
   </div>
```

Il risultato sarà questo:

![Col-lg-4](/Users/emiliano/Desktop/scuola/bootstrap italia/img/col-lg-4.png)

Per ottenere questo risultato ho creato un foglio di stile style.css l'ho  messo nella root del sito in una cartella che ho chiamato css e l'ho linkato al documento html in questo modo:

```html
<link rel="stylesheet" href="css/style.css">
```

All'interno del foglio di stile ho inserito due classi:

```css
    .sidebar{
        background-color: #333;
        background-clip: content-box;
        color: #fff;
    }
    .news{
        background-color:antiquewhite;
        background-clip: content-box;
    }
```
Ho poi applicato le classi `.sidebar` e `.news` alle colonne in questo modo:

```html
<div class="container">
       <div class="row">
           <div class="col-lg-4 news">Colonna 1</div>
           <div class="col-lg-4 news">Colonna 2</div>
           <div class="col-lg-4 sidebar">Sidebar</div>
       </div>
</div>
```

Se adesso volessimo inserire sull'area a sinistra, quella dei contenuti non due news le ultime 6 news come potremmo fare?

Se provo ad inserire i div così:

```html
    <div class="container">
        <div class="row">
            <div class="col-lg-4 news">News 1</div>
            <div class="col-lg-4 news">News 2</div>
            <div class="col-lg-4 sidebar">Sidebar</div>
            <div class="col-lg-4 news">News 3</div>
            <div class="col-lg-4 news">News 4</div>
            <div class="col-lg-4 news">News 5</div>
            <div class="col-lg-4 news">News 6</div>
        </div>
    </div>
```

Il risultato sarà questo:

![sidebar](/Users/emiliano/Desktop/scuola/bootstrap italia/img/6news.png)

Sicuramente non è il risultato sperato.



**Qui è il caso di utilizzare le colonne annidate!!!**

Quindi torniamo al codice iniziale:

```html
<div class="container">
       <div class="row">
         	 
           <!-- Area News -->
           <div class="col-lg-4 news">News 1</div>
           <div class="col-lg-4 news">News 2</div>
          
           <!-- Sidebar -->
           <div class="col-lg-4 sidebar">Sidebar</div>
       </div>
</div>
```

Le tre colonne `.col-lg-4` dovranno cambiare, pertanto l'**area news** che occupa i 2/3 della viewport diventerà un unico elemento class `.col-lg-8 `

```html
...
<!-- Area news -->
<div class="col-lg-8 content"></div>
<!-- Sidebar -->
<div class="col-lg-4 sidebar">Sidebar</div>
...
```

Le due colonne relative alle news con classe `.news` saranno annidate dentro alla `.col-lg-8 .content. `

> Nota bene: I due elementi avevano entrambi class **.col-lg-4** ma annidati gli ho dato class **.col-lg-6**. Questo perchè come ho detto sopra ogni riga annidata contiene a sua volta una griglia di 12 colonne che si possono riempire esattamente come quella della griglia di primo livello.



Il risultato finale sarà questo:

```html
    <div class="container">
        <div class="row">
            <!-- Area news -->
            <div class="col-lg-8 content">
                <!-- riga annidata e nuova griglia di 12 colonne -->
                <div class="row">
                    <div class="col-lg-6 news">News 1</div>
                    <div class="col-lg-6 news">News 2</div>
                </div>
                <!-- fine righe e colonne annidate -->
            </div>
            <!-- Sidebar -->
            <div class="col-lg-4 sidebar">Sidebar</div>
        </div>
    </div>
```



## Prova a casa

1. Ad inserire 6 news e ad ottenere questo risultato sia nella viewport **Large** che **ExtraLarge**

![sidebar6news](/Users/emiliano/Desktop/scuola/bootstrap italia/img/6newsok.png)



2. Ad ottenere che nella viewport **Medium** le news vengano disposte su un'unica colonna così:

![md view](/Users/emiliano/Desktop/scuola/bootstrap italia/img/md-view.png)



3. Ad ottenere che nella viewport **ExtraSmall** e **Small** gli elementi siano disposti così:

![XS e SM](/Users/emiliano/Desktop/scuola/bootstrap italia/img/xs-sm-view.png)