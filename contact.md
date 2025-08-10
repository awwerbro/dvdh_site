---
layout: page
bigimg:
  - "/img/big-imgs/contact/111_banner.jpg": (c) Joke Puers
  - "/img/big-imgs/contact/Jan-banner_small.jpg": (c) Jan Verstraete
---

# VOLGENDE KAMPEN

<div id="kampen"></div>

<script>
(function() {
  const startEditie = 119; // Winter 2025 is 119e editie
  const now = new Date();
  let jaar = 2025;
  let editie = startEditie;
  let kampen = [];

  function winter(y, nr) {
    return {
      editie: nr,
      type: "winter",
      start: new Date(y, 11, 25), // december (11)
      einde: new Date(y, 11, 31),
      startTijd: "14h00",
      eindTijd: "12h00",
      plaats: "Lokeren (Domein Verloren Bos)",
      extra: ""
    };
  }

  function zomer(y, nr) {
    return {
      editie: nr,
      type: "zomer",
      start: new Date(y, 7, 1), // augustus (7)
      einde: new Date(y, 7, 8),
      startTijd: "16h00",
      eindTijd: "12h00",
      plaats: "Merelbeke (Domein Ten Berg)",
      extra: " Het concert gaat eveneens door in Domein Ten Berg, op 7 augustus om 16h00."
    };
  }

  // Bouw een lijst van kampen vooruit
  let type = "winter";
  while (kampen.length < 20) {
    if (type === "winter") {
      kampen.push(winter(jaar, editie));
      jaar++;
      type = "zomer";
    } else {
      kampen.push(zomer(jaar, editie));
      editie++;
      type = "winter";
    }
  }

  // Zoek eerstvolgende kamp
  let nextIndex = kampen.findIndex(k => k.start > now);
  if (nextIndex === -1) nextIndex = 0;

  const volgende = kampen[nextIndex];
  const daarna = kampen[nextIndex + 1];

  function formatKamp(k) {
    const maandNaam = (k.type === "winter") ? "december" : "augustus";
    return `<strong>De ${k.editie}e Dagen van de Huismuziek</strong> gaan door van ${k.start.getDate()} ${maandNaam} ${k.start.getFullYear()} (${k.startTijd}) tot en met ${k.einde.getDate()} ${maandNaam} ${k.einde.getFullYear()} (${k.eindTijd}) in ${k.plaats}.${k.extra}`;
  }

  document.getElementById("kampen").innerHTML = `
    <p>${formatKamp(volgende)}</p>
    <p>${formatKamp(daarna)}</p>
  `;
})();
</script>

### Prijs
Deelname aan het winter- of zomerkamp kost €280. 

### !!! KORTINGSACTIE !!!
Neem een nieuwe deelnemer mee en krijg korting op het inschrijvingsgeld! 

KORTING? WELKE KORTING?
Per nieuwe deelnemer die je aanbrengt krijg je een korting van €40 op het inschrijvingsgeld. 
Als je 1 lid aanbrengt betaal je zo slechts €240, als je 2 nieuwe leden aanbrengt €200 enzovoort.

HOE KRIJG IK DEZE KORTING?
Volg de standaard inschrijvingsprocedure zoals hieronder beschreven, en stuur daarna een mailtje naar ikwilmee@dagenvandehuismuziek.be met de naam van de nieuwe deelnemer(s) die je aanbrengt. Van zodra de nieuwe deelnemers ingeschreven zijn, krijg je van ons een bevestigingsmailtje en wordt het kortingsbedrag teruggestort op jouw rekening.


# HOE INSCHRIJVEN?
Ging je kind al eerder mee op kamp? Leuk!
Het enige dat je hoeft te doen is je kind inschrijven voor ons volgende kamp via [deze link](https://app.assistonline.eu/mvc/activity?key=6b8c4ec5-56a6-402e-82fb-6c645b2fe288). 

Je zal na inschrijving automatisch doorverwezen worden naar onze digitale betaalomgeving voor de betaling van het inschrijvingsgeld (€280).
Wil je graag jullie persoonsgegevens in onze database nog eens controleren of wijzigen maar heb je je login niet meer? Stuur een mailtje naar ikwilmee@dagenvandehuismuziek.be

Gaat je kind voor de eerste keer mee? Ook leuk!
Voordat je je kind kan inschrijven voor het volgende kamp, vragen we je om je kind eerst aan te sluiten bij de vzw. Dit is eenmalig en volledig kosteloos, en kan via [deze link](https://www.mijnassist.be/NL/3d894289-0304-4cb7-9e7c-07b6f9ec7c8a/waitinglist/subscribe).

Eens de aansluiting van jouw kind bij de vzw goedgekeurd is, zal je een uitnodiging ontvangen om je kind in te schrijven voor het eerstvolgende kamp.

## OPMERKINGEN
* Heb je vragen of opmerkingen? Laat het ons weten via ikwilmee@dagenvandehuismuziek.be.
* Wij aanvaarden een maximum van 50 deelnemers per kamp (behoudens coronamaatregelen). Geen paniek: we werken met een wachtlijst, dus je kind maakt altijd kans om nog mee te kunnen, ook nadat de grens van 50 inschrijvingen bereikt is.
* De inschrijving van je kind annuleren kan kosteloos tot 3 kalenderweken voor aanvang van het kamp, anders wordt het inschrijvingsgeld slechts voor 50% terugbetaald (behalve bij ziekte).
* Door je kind in te schrijven voor onze kampen geef je toestemming dat foto’s van het kamp voor publicitaire doeleinden gebruikt mogen worden (bijvoorbeeld op onze website), tenzij je uitdrukkelijk het tegendeel vermeldt.
