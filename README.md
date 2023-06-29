# level-0

## Enklaste React Applikationen

```bash
mkdir react-app
cd react-app
curl -L https://raw.githubusercontent.com/miwashi-edu/edu-react-intro/level-0/resources/index-level-0.html -o index.html
npm init -y
npm pkg set scripts.start="http-server"
npm install react react-dom
npm install -D http-server
npm start
```
[Klicka här för att starta webbläsaren på port 8080](http://localhost:8080)

## Vi putsar lite

> Vi lägger till en public mapp  
> Vi lägger till en favicon  
> Vi startar på port 3000 istället

```bash
npm pkg set scripts.start="http-server public -p 3000"
mkdir public
mv index.html public/
curl https://www.jensenyh.se/favicon.ico -o ./public/favicon.ico
npm pkg set scripts.start="http-server public -p 3000"
```
[Klicka här för att starta webbläsaren på port 3000](http://localhost:3000)

## Förklaringar

### index.html

> Vi läser in **react** och **react-dom** ramverket från *unpkg.com* istället för med *npm install*.  
> Vi läser in **babel** från *unpkg.com, den behövs för att transpilera **jsx** filer till **js**.  
> *Transpilera* betyder att översätta från ett människoläst språk till ett annat. 
> Då vi översätter till språk som datorn ska läsa används ordet *kompilera*.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello React!</title>
    <script src="https://unpkg.com/react/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  </head>
  <body>
    <div id="root"></div>
    <script type="text/babel">
      ReactDOM.render(
        React.createElement('h1', null, 'Hello, world!'),
        document.getElementById('root')
      );
    </script>
  </body>
</html>
```

> [Babel](https://babeljs.io) är en javascript kompilator (transpilator), den används för att översätta 
> javascript till den version (ECMAScript ES5/ES6) som webbläsare förstår. Utan den är koden oförstålig
> för webbläsaren.
 

> [unpkg](unpkg.com) Är en Content Delivery Network (CDN), där kan man hitta de flesta publika javascript
> ramverk och filer.

> [favicon](https://en.wikipedia.org/wiki/Favicon) är en fil som ofta heter favicon.ico, man kan lägga den 
> så att webbläsaren hittar den på http://localhost:3000/favicon.ico, eller så kan man använda en meta tagg 
> och lägga den var man vill. Det är ikonen du ser i fliken på webbläsaren.
```html
<link rel="icon" type="image/png" href="img/favicon.png">
```

> **public** är ett namn man ofta väljer för statiska filer, dvs filer som inte ändrar sig mellan anrop. 
> I en React application är *public* standard, men mång andra namn kan finnas.
> Det kommer från den tiden då en webbläsare enbart var en mapp på nätet och inte kunde köra
> dynamiskt innehåll överhuvudtaget.

## Bash kommandon vi använt.
[ls - list directory content](https://man7.org/linux/man-pages/man1/ls.1.html)
: Vi listar innehållet i en katalog

[cd - change directory](https://man7.org/linux/man-pages/man1/cd.1p.html)  
: Vi ändrar arbetskatalog till ny

[mv - move](https://man7.org/linux/man-pages/man1/mv.1.html)  
: Vi flyttar fil. (I Unix är även kataloger filer.) Move används också för att byta namn på filer.

[mkdir - make directory](https://man7.org/linux/man-pages/man1/mkdir.1.html)
: Vi skapar en ny fil (katalog)

[curl - command line url](https://man7.org/linux/man-pages/man1/curl.1.html)
: En slags textbaserad webbläsare

[npm Node Package Manager](https://www.npmjs.com)
: En beroendehanterare (paket hanterare) för Node (alternativ Yarn, Yarn Berry, pnmp, Bower, Volta eller Rush).

[npm pkg](https://www.npmjs.com/package/pkg)
: Ett NPM kommando för att ändra på package.json.


# level-1