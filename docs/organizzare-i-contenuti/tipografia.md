---
layout: docs
group: organizzare-i-contenuti
toc: true
title: Tipografia
description: Documentazione sulla gestione della tipografia, come intestazioni, paragrafi, citazioni, elenchi e altro.
---

Bootstrap imposta alcune proprietà di base per la tipografia e gli stili dei
link. Quando è necessario un maggiore controllo, fornisce delle
[classi di utilità testuali]({{ site.baseurl }}/docs/organizzare-i-contenuti/testo/).

## Famiglie di Caratteri

Come descritto in dettaglio nel capitolo sullo UI Kit, le Linee Guida di Design
suggeriscono di usare le seguenti famiglie di caratteri:

- il font senza grazie, o _sans serif_, **Titillium Web**.
- il font graziato, o _serif_, **Lora**.
- il font _monospace_ con dimensioni di caratteri normalizzate **Roboto Mono**.

### Titillium Web

È la famiglia di caratteri utilizzata per i contenuti web, per cui di norma non
è necessario applicarlo esplicitamente. In caso si renda necessario è possibile
utilizzare la classe `font-sans-serif`.

{% comment %}Example name: Titillium Web{% endcomment %}
{% capture example %}
<p class="font-sans-serif">ABCDEFGHIJKLMNOPQRSTUVWXYZ</p>
<p class="font-sans-serif">abcdefghijklmnopqrstuvwxyz</p>
<p class="font-sans-serif">0123456789</p>
{% endcapture %}{% include example.html content=example %}

### Lora

È un carattere più adatto a testi lunghi, introdotto per la sua leggibilità,
nato espressamente per la lettura su display. Può essere utilizzato applicando
la classe `font-serif`.

{% comment %}Example name: Lora{% endcomment %}
{% capture example %}
<p class="font-serif">ABCDEFGHIJKLMNOPQRSTUVWXYZ</p>
<p class="font-serif">abcdefghijklmnopqrstuvwxyz</p>
<p class="font-serif">0123456789</p>
{% endcapture %}{% include example.html content=example %}

### Roboto Mono

È una famiglia di caratteri adatta ad essere utilizzata per la rappresentazione
di numeri, codici, calcoli matematici, esempi con linguaggi di programmazione.
Per il suo utilizzo, è sufficiente usare la classe `font-monospace`.

{% comment %}Example name: Roboto{% endcomment %}
{% capture example %}
<p class="font-monospace">ABCDEFGHIJKLMNOPQRSTUVWXYZ</p>
<p class="font-monospace">abcdefghijklmnopqrstuvwxyz</p>
<p class="font-monospace">0123456789</p>
{% endcapture %}{% include example.html content=example %}

## Tipografia responsive

Bootstrap Italia ridimensiona testo e alcune propietà dei componenti modificando
il `font-size` dell'elemento radice, con una media query che imposta dimensioni
lievemente maggiori per schermi con dimensioni maggiori di _576px_. Questa
impostazione, unita all'utilizzo di dimensioni in `rem` o in semplici valori
numerici all'interno del CSS, fa sì che testo e altre proprietà occupino più
spazio quando lo schermo lo permette:

```scss
html {
  font-size: 16px;
  @include media-breakpoint-up(sm) {
    font-size: 18px;
  }
}
```

## Intestazioni

Tutte le intestazioni HTML, da `<h1>` fino a `<h6>`, sono disponibili, anche se
è buona norma non utilizzare più di 4 livelli di intestazione.

Nel caso in cui si voglia presentare il testo nello stesso stile delle
intestazioni, ma non sia possibile utilizzare l'elemento HTML appropriato,
sono disponibili anche classi di tipo `.h1`, `.h2`, ecc.

{% comment %}Example name: Intestazioni{% endcomment %}
{% capture example %}
<h1 class="no_toc">Intestazione di tipo h1</h1>
<h2 class="no_toc">Intestazione di tipo h2</h2>
<h3 class="no_toc">Intestazione di tipo h3</h3>
<h4 class="no_toc">Intestazione di tipo h4</h4>
<h5 class="no_toc">Intestazione di tipo h5</h5>
<h6 class="no_toc">Intestazione di tipo h6</h6>

<p class="h1">Stile h1</p>
<p class="h2">Stile h2</p>
<p class="h3">Stile h3</p>
<p class="h4">Stile h4</p>
<p class="h5">Stile h5</p>
<p class="h6">Stile h6</p>
{% endcapture %}{% include example.html content=example %}

Queste le dimensioni nel dettaglio:

<table>
  <thead>
    <tr>
      <th>Intestazione</th>
      <th>Mobile</th>
      <th>Schermo > 576px</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <p class="h1">h1</p>
      </td>
      <td>Bold, 40px/48px</td>
      <td>Bold, 48px/60px</td>
    </tr>
    <tr>
      <td>
        <p class="h2">h2</p>
      </td>
      <td>Bold, 32px/40px</td>
      <td>Bold, 40px/48px</td>
    </tr>
    <tr>
      <td>
        <p class="h3">h3</p>
      </td>
      <td>Bold, 28px/32px</td>
      <td>Bold, 32px/40px</td>
    </tr>
    <tr>
      <td>
        <p class="h4">h4</p>
      </td>
      <td>SemiBold, 24px/28px</td>
      <td>SemiBold, 28px/40px</td>
    </tr>
    <tr>
      <td>
        <p class="h5">h5</p>
      </td>
      <td>Regular, 20px/24px</td>
      <td>Regular, 24px/40px</td>
    </tr>
    <tr>
      <td>
        <p class="h6">h6</p>
      </td>
      <td>SemiBold, 16px/24px</td>
      <td>SemiBold, 18px/28px</td>
    </tr>
  </tbody>
</table>

### Intestazione h1 in evidenza

Gli elementi di intestazione tradizionali sono progettati per funzionare al
meglio nel contesto della pagina. Nel caso sia necessario mettere in ulteriore
evidenza un'intestazione di tipo `<h1>`, si può prendere in considerazione l'uso
della classe `.display-1`, che restituirà una dimensione sensibilmente più
grande.

{% comment %}Example name: Intestazione h1 in evidenza{% endcomment %}
{% capture example %}
<h1 class="no_toc display-1">Intestazione di tipo h1 in evidenza</h1>
{% endcapture %}{% include example.html content=example %}

<!-- ### Personalizzazione delle intestazioni

È possibile utilizzare le classi di utilità incluse in Bootstrap per
dare uno stile diverso per testi di intestazione secondaria.

{% capture example %}

<h4>Intestazione <small class="text-muted">con testo secondario</small></h4>
{% endcapture %}{% include example.html content=example %}

--> 

## Paragrafi

Il semplice paragrafo prevede una dimensione di testo e un'interlinea di
`16px/24px` per dispositivi mobili, e di `18px/28px` per schermi con dimensioni
maggiori di 576px.

{% comment %}Example name: Paragrafi contenuti{% endcomment %}
{% capture example %}
<p>Ullamco laboris nisi ut aliquid ex ea commodi consequat. Curabitur blandit tempus ardua ridiculus sed magna. Curabitur est gravida et libero vitae dictum. Phasellus laoreet lorem vel dolor tempus vehicula. Magna pars studiorum, prodita quaerimus.</p>
<p>Ullamco laboris nisi ut aliquid ex ea commodi consequat. Curabitur blandit tempus ardua ridiculus sed magna. Curabitur est gravida et libero vitae dictum. Phasellus laoreet lorem vel dolor tempus vehicula. Magna pars studiorum, prodita quaerimus.</p>
{% endcapture %}{% include example.html content=example %}

Per una lettura più confortevole, è buona norma mantenere la lunghezza di un paragrafo
compresa tra 45 e 74 caratteri. Per testo su colonne multiple, si considera una
lunghezza compresa tra 40 e 50 caratteri. Per i testi a margine la lunghezza
minima è di 12-15 caratteri.

### Paragrafi in evidenza

Per mettere in risalto un paragrafo è sufficiente aggiungere la classe `.lead`.

{% comment %}Example name: Paragrafi in evidenza{% endcomment %}
{% capture example %}
<p class="lead">Paragrafo in evidenza</p>
{% endcapture %}{% include example.html content=example %}

### Personalizzazione dei paragrafi

È possibile stilizzare correttamente lo stile anche nel caso vengano utilizzati
semplicemente gli elementi HTML5 per il trattamento di testo.

{% comment %}Example name: Markup semantico nei paragrafi{% endcomment %}
{% capture example %}
<p>Esempio di testo <u>sottolineato</u>.</p>
<p>Esempio di testo <mark>evidenziato</mark>.</p>
<p>Esempio di testo <em>corsivo</em>.</p>
<p>Esempio di testo <strong>in grassetto</strong>.</p>
<p>Esempio di testo <small>rimpicciolito</small>.</p>
<p>Esempio di testo <ins>aggiuntivo</ins>.</p>
<p>Esempio di testo <del>cancellato</del> o <s>invalido</s>.</p>
<p>Esempio di testo <code>monospace</code>.</p>
{% endcapture %}{% include example.html content=example %}

Le classi `.mark` e `.small` sono disponibili anche per applicare gli stessi
stili di `<mark>` e `<small>` evitando eventuali implicazioni semantiche
indesiderate che i tag porterebbero con sé.

È possibile sfruttare le classi di Bootstrap anche per modificare allineamento,
stile, peso e colore del testo. Per questo, si può fare riferimento alla
documentazione delle [utilità di testo]({{ site.baseurl }}/docs/organizzare-i-contenuti/testo/)
e [utilità di colore]({{ site.baseurl }}/docs/utilities/colori/).

### Link

{% capture callout %}

#### Accessibilità

È fondamentale evidenziare i link presenti in un paragrafo in modo adeguato, utilizzando la forma (grassetto, sottolineato) oltre al colore per indicare la presenza di un collegamento ipertestuale.
{% endcapture %}{% include callout.html content=callout type="accessibility" %}

Nel rispetto delle regole di accessibilità vigenti, Bootstrap Italia mantiene la sottolineatura ai link di tipo `<a>`. Nel caso di link già in evidenza (menu principali, liste di link, link in grassetto, ecc.), è possibile rimuovere la sottolineatura utilizzando la classe `.text-decoration-none`.

{% comment %}Example name: Link{% endcomment %}
{% capture example %}
<p>Esempio di <a href="#">link normale</a>.</p>
<p>Esempio di <a href="#" class="text-decoration-none fw-bold">link in grassetto senza sottolineatura</a>.</p>
{% endcapture %}{% include example.html content=example %}

## Abbreviazioni

Implementazione stilizzata dell'elemento HTML `<abbr>` per abbreviazioni e
acronimi per mostrare la versione espansa sull' hover. Le abbreviazioni hanno
una sottolineatura predefinita e ottengono un cursore di aiuto per fornire un
contesto aggiuntivo al passaggio del mouse e agli utenti delle tecnologie
assistive.

Aggiungi `.initialism` a un'abbreviazione per una dimensione del font
leggermente più piccola.

{% comment %}Example name: Abbreviazioni{% endcomment %}
{% capture example %}
<p><abbr title="attribute">attr</abbr></p>
<p><abbr title="HyperText Markup Language" class="initialism">HTML</abbr></p>
{% endcapture %}{% include example.html content=example %}

## Citazioni

Per citare blocchi di contenuti da un'altra fonte all'interno del documento.
Racchiudi ogni <abbr title="HyperText Markup Language">HTML</abbr> all'interno
di un `<blockquote class="blockquote">` come la citazione.

{% comment %}Example name: Citazioni{% endcomment %}
{% capture example %}
<blockquote class="blockquote">
  <p class="mb-0">Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt sequi eos ratione.</p>
</blockquote>
{% endcapture %}{% include example.html content=example %}

### Citare una fonte

Aggiungi un `<footer class="blockquote-footer">` per identificare la fonte.
Includi il nome delle fonte di origine in `<cite>`.

{% comment %}Example name: Citazioni con fonte{% endcomment %}
{% capture example %}
<blockquote class="blockquote">
  <p class="mb-0">Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt sequi eos ratione.</p>
  <footer class="blockquote-footer">Nome Cognome da <cite title="Titolo fonte">Titolo fonte</cite></footer>
</blockquote>
{% endcapture %}{% include example.html content=example %}

### Allineamento

Utilizza le utilità di testo necessarie per modificare l'allineamento del tuo
blockquote.

{% comment %}Example name: Citazione, centrata{% endcomment %}
{% capture example %}
<blockquote class="blockquote text-center">
  <p class="mb-0">Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt sequi eos ratione.</p>
  <footer class="blockquote-footer">Nome Cognome da <cite title="Titolo fonte">Titolo fonte</cite></footer>
</blockquote>
{% endcapture %}{% include example.html content=example %}

{% comment %}Example name: Citazione, a destra{% endcomment %}
{% capture example %}
<blockquote class="blockquote text-end">
  <p class="mb-0">Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt sequi eos ratione.</p>
  <footer class="blockquote-footer">Someone famous in <cite title="Source Title">Source Title</cite></footer>
</blockquote>
{% endcapture %}{% include example.html content=example %}

### Semplice

Aggiungendo la classe `.blockquote-simple` si ottiene una versione base del Blockquote.

{% comment %}Example name: Citazione, base{% endcomment %}
{% capture example %}
<blockquote class="blockquote blockquote-simple">
  <p class="mb-0">Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt sequi eos ratione.</p>
</blockquote>
{% endcapture %}{% include example.html content=example %}

### Card

Aggiungendo la classe `.blockquote-card` si ottiene un Blockquote di tipo card.

{% comment %}Example name: Citazione, card{% endcomment %}
{% capture example %}
<blockquote class="blockquote blockquote-card">
  <p>Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt sequi eos ratione.</p>
  <footer class="blockquote-footer"><cite title="Titolo fonte">Titolo fonte</cite></footer>
</blockquote>
{% endcapture %}{% include example.html content=example %}

Aggiungendo un'ulteriore classe `.dark` si ottiene un Blockquote card scuro.

{% comment %}Example name: Citazione, card con sfondo scuro{% endcomment %}
{% capture example %}
<blockquote class="blockquote blockquote-card dark">
  <p>Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt sequi eos ratione.</p>
  <footer class="blockquote-footer"><cite title="Titolo fonte">Titolo fonte</cite></footer>
</blockquote>
{% endcapture %}{% include example.html content=example %}

## Liste

Rimuovi il predefinito `list-style` e il margine sinistro sugli elementi
elenco (solo per i figli diretti). **Questo si applica solo agli elementi della 
lista che sono figli diretti**, il che significa che dovrai aggiungere la classe
per tutti gli elenchi annidati.

{% comment %}Example name: Lista senza stile{% endcomment %}
{% capture example %}
<ul class="list-unstyled">
  <li>Lorem ipsum dolor sit amet</li>
  <li>Consectetur adipiscing elit</li>
  <li>Integer molestie lorem at massa</li>
  <li>Facilisis in pretium nisl aliquet</li>
  <li>Nulla volutpat aliquam velit
    <ul class="list-unstyled">
      <li>Phasellus iaculis neque</li>
      <li>Purus sodales ultricies</li>
      <li>Vestibulum laoreet porttitor sem</li>
      <li>Ac tristique libero volutpat at</li>
    </ul>
  </li>
  <li>Faucibus porta lacus fringilla vel</li>
  <li>Aenean sit amet erat nunc</li>
  <li>Eget porttitor lorem</li>
</ul>
{% endcapture %}{% include example.html content=example %}

### Inline

Rimuovi i punti elenco di una lista e applica un leggero `margin` con una
combinazione di due classi, `.list-inline` e `.list-inline-item`.

{% comment %}Example name: Lista inline{% endcomment %}
{% capture example %}
<ul class="list-inline">
  <li class="list-inline-item">Lorem ipsum</li>
  <li class="list-inline-item">Phasellus iaculis</li>
  <li class="list-inline-item">Nulla volutpat</li>
</ul>
{% endcapture %}{% include example.html content=example %}

### Allineamento lista descrizione

Allineare i termini e le descrizioni orizzontalmente utilizzando le classi
predefinite del nostro sistema di griglia. Per termini più lunghi, puoi
facoltativamente aggiungere la classe `.text-truncate` per troncare il testo
con un `ellipsis`.

{% comment %}Example name: Lista, allineamento descrizione{% endcomment %}
{% capture example %}
<dl class="row">
  <dt class="col-sm-3">Lista descrizioni</dt>
  <dd class="col-sm-9">Una lista di discrezioni è lo strumento ideale per definire dei termini.</dd>

  <dt class="col-sm-3">Euismod</dt>
  <dd class="col-sm-9">
    <p>Vestibulum id ligula porta felis euismod semper eget lacinia odio sem nec elit.</p>
    <p>Donec id elit non mi porta gravida at eget metus.</p>
  </dd>

  <dt class="col-sm-3">Malesuada porta</dt>
  <dd class="col-sm-9">Etiam porta sem malesuada magna mollis euismod.</dd>

  <dt class="col-sm-3 text-truncate">Testo troncato: questo testo troppo lungo verrà troncato</dt>
  <dd class="col-sm-9">Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.</dd>

  <dt class="col-sm-3">Annidamento</dt>
  <dd class="col-sm-9">
    <dl class="row">
      <dt class="col-sm-4">Lista descrizione annidata</dt>
      <dd class="col-sm-8">Aenean posuere, tortor sed cursus feugiat, nunc augue blandit nunc.</dd>
    </dl>
  </dd>
</dl>
{% endcapture %}{% include example.html content=example %}
