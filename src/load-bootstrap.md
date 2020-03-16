## Caricare la libreria di Bootstrap Italia

Per utilizzare il codice compilato di Bootstrap Italia nel tuo progetto, è sufficiente scaricare ed includere nella pagina HTML alcuni file, tra cui un file CSS, un Javascript, il tutto scaricabile  qui:

[Scarica Bootstrap Italia v1.3.10](https://github.com/italia/bootstrap-italia/releases/download/v1.3.10/bootstrap-italia.zip)

##### Importante!

È sempre consigliabile utilizzare la **versione più recente della libreria e mantenerla aggiornata** sui propri progetti.

La versione più recente tra le release di progetto contiene anche tutti i miglioramenti e le correzioni disponibili fino ad oggi.

Le librerie Javascript e CSS di Bootstrap Italia personalizzano e comprendono anche il codice originale di **Bootstrap 4.3.1**, ereditandone quindi tutte i selettori, le funzionalità, ecc., che sono consultabili al sito di Bootstrap stesso.

Di seguito le informazioni per l’utilizzo dei singoli file.

### CSS

Una volta scaricato e decompresso il file, all’interno della cartella `css` sarà presente un file CSS minificato (`bootstrap-italia.min.css`) 

Per includere questo file all’interno del tuo progetto sarà quindi sufficiente aggiungere il tag `<link>` di seguito riportato all’interno del tag `<head>` della pagina, prima di ogni altro CSS già presente, eventualmente correggendo il riferimento al percorso del file:

```html
<link rel="stylesheet" href="./bootstrap.min.css">
```

### Javascript

All’interno della cartella `js` saranno invece presenti due file, che si differenziano soltanto per l’inclusione *in linea* delle librerie *jQuery*, *popper.js* e *Owl Carousel* (quest’ultimo necessario soltanto se presenti componenti di tipo [Carousel](https://italia.github.io/bootstrap-italia/docs/componenti/carousel)). Vediamo nel dettaglio di cosa si tratta:

| JS files                         | Popper      | jQuery      | OwlCarousel |
| :------------------------------- | :---------- | :---------- | :---------- |
| `bootstrap-italia.bundle.min.js` | **Incluso** | **Incluso** | **Incluso** |
| `bootstrap-italia.min.js`        | Non Incluso | Non Incluso | Non Incluso |

In questo caso, dopo aver copiato i file all’interno del vostro progetto, sarà sufficiente inserire una versione dei tag `<script>` di seguito riportati alla fine della pagina HTML, giusto prima della chiusura del tag `<body>`. Si potrà quindi **scegliere** se includere la versione `*.bundle.*` o caricare i singoli file separatamente (questo può rendersi necessario, ad esempio, se jQuery è già incluso nel vostro sito per altri motivi).



### Fonts

È necessario anche includere i file relativi ai font referenziati nel CSS, mantenendo i path dei singoli font utilizzato nei [file sorgente della libreria](https://github.com/italia/bootstrap-italia/releases/tag/v1.3.10). Il path di base della cartella dei font può essere impostato utilizzando la variabile globale **prima** del caricamento della libreria Javascript di Bootstrap Italia:

Copia

```html
<script>window.__PUBLIC_PATH__ = '/bootstrap-italia/dist/fonts'</script>
```

Se tale variabile non è valorizzata, i font saranno cercati all’interno di una cartella `/bootstrap-italia/dist/fonts/`.



### Icone

Le icone a disposizione sono un componente assolutamente opzionale e sono pubblicate nella libreria sotto forma di sprite SVG `/bootstrap-italia/dist/svg/`, le cui singole SVG sorgenti sono presenti nel repository.

Per informazioni, si può fare riferimento alla [documentazione sull’utilizzo delle icone](https://italia.github.io/bootstrap-italia/docs/utilities/icone/).



#### Versione “bundle”

Includendo la versione `*.bundle.*`, non sarà necessario aggiungere ulteriori riferimenti a jQuery, Popper.js e Owl Carousel, in quanto già inclusi nel file `bootstrap-italia.bundle.min.js`.

Copia

```html
<script src="./bootstrap-italia.bundle.min.js"></script>
```



#### Versione semplice

Al contrario, nel caso si preferisca caricare jQuery, Popper.js e Owl Carousel separatamente, sarà necessario includere i tag `` come mostrato di seguito:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/owl.carousel.min.js" crossorigin="anonymous"></script>
<script src="./bootstrap-italia.min.js"></script>
```



## Pagina HTML di esempio [*Starter template*]

Nota: 

> Lo starter template quindi sarà diverso da quello originale in quanto la risorsa **bootstrap-italia.bundle.min.js** contiene tutte le componenti JS che servono al framework. 
>
> **Dovrete però scaricare tutto in locale!!!**

In breve, si dovrebbe ottenere qualcosa di simile a ciò che segue:

```html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    
    <!-- CSS -->
    <link rel="stylesheet" href="./bootstrap-italia.min.css">
  </head>
  <body>
    <h1>Hello, world!</h1>
    <!-- JS -->
    <script src="./bootstrap-italia.bundle.min.js"></script>
  </body>
</html>
```

Questo è tutto ciò che è sufficiente per avere a disposizione le funzionalità e gli stili di Bootstrap Italia.