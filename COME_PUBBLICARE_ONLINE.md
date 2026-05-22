# Come pubblicare Atchii online con GitHub Pages

## Metodo semplice

1. Vai su GitHub.
2. Crea un nuovo repository chiamato `atchii`.
3. Carica dentro il repository tutti i file di questa cartella `atchii-online`.
4. Apri `Settings`.
5. Vai su `Pages`.
6. In `Build and deployment`, scegli:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/root`
7. Salva.

Dopo qualche minuto il sito sarà online a un indirizzo simile:

`https://alyanna02.github.io/atchii/`

## File necessari

- `index.html`
- `atchii-config.js`
- `.nojekyll`
- `README.md`

## Nota su Unity

Il gioco platform con addizioni è già eseguibile online perché è stato integrato in HTML e JavaScript.

La cartella Unity separata contiene il prototipo sorgente Unity. Per pubblicare un gioco Unity vero nel sito servirà esportarlo da Unity come WebGL e poi inserirlo in una pagina web.

## Nota su Atchii AI con ChatGPT/OpenAI

Il sito su GitHub Pages può mostrare la chat, ma GitHub Pages non può eseguire Python.

Per usare ChatGPT/OpenAI serve pubblicare anche il backend `atchii-backend` su un servizio esterno, per esempio Render, Railway, Fly.io o un server tuo.

Dopo aver pubblicato il backend, apri `atchii-config.js` e sostituisci:

```javascript
window.ATCHII_API_URL = "http://127.0.0.1:5050/api/atchii";
```

con l'indirizzo online del backend, per esempio:

```javascript
window.ATCHII_API_URL = "https://atchii-backend.onrender.com/api/atchii";
```
