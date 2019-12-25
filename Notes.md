# Qualche annotazione

## Gitignore

Stavo guardando cosa è sicuro aggiungere al file `.gitignore` per rendere la repository più pulita e [qui](https://discourse.gohugo.io/t/should-i-add-resources-to-gitignore/20064) dicono di aggiungere:

```
/public
/node_modules
/resources
```
La cartella `public` effettivamente viene generata da Netlify quindi si può evitare di tracciarla

## Archetypes

Ho trovato la documentazione per creare nuovi contentuti sia come [Archetypes](https://gohugo.io/content-management/archetypes/) che come [Content Types](https://gohugo.io/content-management/types/). E' veramente una figata perchè puoi creare dei template con anche commenti che metti tu e associarli a nuovi comandi come:
```
hugo new --kind teaching teaching/nome_corso
```
Questo comando prima non c'era e quindi adesso è possibile aggiungere poster e corsi in modo automatico nelle rispettive cartelle. Se cambi l'archetipo (nella cartella `\themes\hugo-academic\archetypes`) cambi il template che si crea quando lanci il comando precedente. Veramente figo!