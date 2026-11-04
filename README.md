# Proof of Concept — Git Push Team

Prove tecnologiche per il capitolato **C2 – NEXUM Concierge** (Eggon S.r.l.).

Un *Proof of Concept* (PoC) risponde a una domanda precisa su una tecnologia
("RubyLLM riesce a instradare le richieste a due provider diversi?", "con la
RAG l'assistente trova la regola giusta nel manuale ferie?") con il minimo
codice indispensabile. I risultati servono a scegliere lo stack per la
*Technology Baseline* dell'RTB e finiscono nella Specifica Tecnica. Il codice
dei PoC si può buttare: il prodotto vero nascerà nel repository `mvp`.

## Struttura

```text
poc/
├── esperimenti/
│   ├── _modello/README.md     la scheda da copiare per ogni nuovo esperimento
│   └── <nome-esperimento>/    un esperimento per cartella, autonomo
│       ├── README.md          la scheda compilata: domanda, come provarlo, esito
│       └── ...                il codice
└── .github/workflows/         collegamento al Project e comando /ore
```

Ogni esperimento è **indipendente**: ha le sue dipendenze e le sue istruzioni
per essere eseguito, così si può cambiare tecnologia da un esperimento
all'altro senza conflitti.

## Come si aggiunge un esperimento

1. Aprite una issue con il modello **Attività** (ruolo, di solito,
   Progettista o Programmatore; stima in ore). Entra da sola nel Project.
2. Create il branch `poc/<numero>-<nome>`, per esempio `poc/8-rubyllm-router`.
3. Copiate `esperimenti/_modello/` in `esperimenti/<nome>/` e compilate la
   scheda **prima** di scrivere codice: la domanda e il criterio di successo.
4. Scrivete il codice, aggiornate la scheda con l'esito e aprite una PR con
   `Closes #<numero>`: la issue passa in *In review*.
5. Il Verificatore prova a eseguirlo seguendo la scheda; se funziona approva
   e unisce.
6. La decisione presa (adottare o scartare la tecnologia) va nel verbale della
   riunione successiva.

## Regole

- **Niente segreti nel repository**: chiavi API, password e token vanno in un
  file `.env` (già escluso da `.gitignore`); nel repository mettete un
  `.env.esempio` con i nomi delle variabili e valori finti.
- **Ore**: si segnano nei commenti della issue con `/ore 2` o
  `/ore 1,5 programmatore`. Regole complete in
  [CONTRIBUTING.md](https://github.com/Git-Push-Team/.github/blob/main/CONTRIBUTING.md).
- `main` si cambia solo con una pull request verificata da un'altra persona.

## Esperimenti

| Esperimento | Domanda | Esito |
| --- | --- | --- |
| _nessuno per ora_ | | |
