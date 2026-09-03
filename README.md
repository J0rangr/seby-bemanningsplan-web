# Seby – Bemanningsplan (web)

Statisk hosting for bemanningsplan-verktøyet. Denne siden inneholder **ingen data** –
alt hentes fra SharePoint via Microsoft Graph etter innlogging med Veidekke-konto.
Kildekoden (med interne notater, alternative løsninger osv.) ligger i det private
repoet `Bemanningsplan`; dette repoet er kun den offentlige, tomme fila som
GitHub Pages serverer.

## Fila

`index.html` – hele appen i én fil. `SEED_STATE` er tom (`"people":[]`); planen
bygges opp i SharePoint-fila `Bemanningsplan-state.json` første gang noen logger inn.

## Gjenstående oppsett

1. **App-registrering i Entra ID** (krever admin) – SPA, delegerte Graph-tillatelser
   `Files.ReadWrite.All` + `Sites.ReadWrite.All`, redirect URI = denne sidens
   GitHub Pages-URL.
2. Lim `clientId` og `tenantId` inn i `GRAPH`-blokken øverst i `index.html`.
3. SharePoint-stedet er forhåndsutfylt: `365veidekke.sharepoint.com/sites/NO-ENT-DistriktSebyAS-IT2`.

Se README i det private `Bemanningsplan`-repoet for detaljert oppskrift og
ferdig utkast til IT-forespørsel.
