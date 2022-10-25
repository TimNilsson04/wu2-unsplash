# 11ty & data file

This is a test of 11ty and data files.

11ty kan hämta data från API och filer. Detta är en test av data från en api sparad som en json fil. Ofta krävs det registrering och en nyckel får att kunna använda en API. Det här exemplet använder en sparar query från Unsplash, men om du vill så kan du registera och köra en query direkt.

https://unsplash.com/developers

## JSON

Svaret från en sökning på unsplash är en array med objekt

```json
        {
            "id": "MYRG0ptGh50",
            "created_at": "2017-10-18T21:10:40Z",
            "updated_at": "2022-10-24T04:02:31Z",
            "promoted_at": null,
            "width": 5331,
            "height": 3554,
            "color": "#260c0c",
            "blur_hash": "LMA[ZBoe5me:f+a#jZoJ1JR+-At5",
            "description": "Pumpkin Twins",
            "alt_description": "jack o'lantern",
            "urls": {
                "raw": "https://images.unsplash.com/photo-1508361001413-7a9dca21d08a?ixid=MnwzNzQ3Nzh8MHwxfHNlYXJjaHwxfHxoYWxsb3dlZW58ZW58MHx8fHwxNjY2NTk0Mjc4&ixlib=rb-4.0.3",
                "full": "https://images.unsplash.com/photo-1508361001413-7a9dca21d08a?crop=entropy&cs=tinysrgb&fm=jpg&ixid=MnwzNzQ3Nzh8MHwxfHNlYXJjaHwxfHxoYWxsb3dlZW58ZW58MHx8fHwxNjY2NTk0Mjc4&ixlib=rb-4.0.3&q=80",
                "regular": "https://images.unsplash.com/photo-1508361001413-7a9dca21d08a?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwzNzQ3Nzh8MHwxfHNlYXJjaHwxfHxoYWxsb3dlZW58ZW58MHx8fHwxNjY2NTk0Mjc4&ixlib=rb-4.0.3&q=80&w=1080",
                "small": "https://images.unsplash.com/photo-1508361001413-7a9dca21d08a?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwzNzQ3Nzh8MHwxfHNlYXJjaHwxfHxoYWxsb3dlZW58ZW58MHx8fHwxNjY2NTk0Mjc4&ixlib=rb-4.0.3&q=80&w=400",
                "thumb": "https://images.unsplash.com/photo-1508361001413-7a9dca21d08a?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwzNzQ3Nzh8MHwxfHNlYXJjaHwxfHxoYWxsb3dlZW58ZW58MHx8fHwxNjY2NTk0Mjc4&ixlib=rb-4.0.3&q=80&w=200",
                "small_s3": "https://s3.us-west-2.amazonaws.com/images.unsplash.com/small/photo-1508361001413-7a9dca21d08a"
            },
            "links": {
                "self": "https://api.unsplash.com/photos/MYRG0ptGh50",
                "html": "https://unsplash.com/photos/MYRG0ptGh50",
                "download": "https://unsplash.com/photos/MYRG0ptGh50/download?ixid=MnwzNzQ3Nzh8MHwxfHNlYXJjaHwxfHxoYWxsb3dlZW58ZW58MHx8fHwxNjY2NTk0Mjc4",
                "download_location": "https://api.unsplash.com/photos/MYRG0ptGh50/download?ixid=MnwzNzQ3Nzh8MHwxfHNlYXJjaHwxfHxoYWxsb3dlZW58ZW58MHx8fHwxNjY2NTk0Mjc4"
            },
            "likes": 1204,
            "liked_by_user": false,
            "current_user_collections": [],
            "sponsorship": null,
            "topic_submissions": {},
            "user": {
                "id": "b5wTrjGb7iQ",
                "updated_at": "2022-10-06T12:50:32Z",
                "username": "cazault",
                "name": "David Menidrey",
                "first_name": "David",
                "last_name": "Menidrey",
                "twitter_username": "cazault",
                "portfolio_url": "http://www.davidmenidrey.com",
                "bio": null,
                "location": "Caen, Normandy, France",
                "links": {
                    "self": "https://api.unsplash.com/users/cazault",
                    "html": "https://unsplash.com/@cazault",
                    "photos": "https://api.unsplash.com/users/cazault/photos",
                    "likes": "https://api.unsplash.com/users/cazault/likes",
                    "portfolio": "https://api.unsplash.com/users/cazault/portfolio",
                    "following": "https://api.unsplash.com/users/cazault/following",
                    "followers": "https://api.unsplash.com/users/cazault/followers"
                },
                "profile_image": {
                    "small": "https://images.unsplash.com/profile-1505684747191-ce10a02bcaa1?ixlib=rb-1.2.1&crop=faces&fit=crop&w=32&h=32",
                    "medium": "https://images.unsplash.com/profile-1505684747191-ce10a02bcaa1?ixlib=rb-1.2.1&crop=faces&fit=crop&w=64&h=64",
                    "large": "https://images.unsplash.com/profile-1505684747191-ce10a02bcaa1?ixlib=rb-1.2.1&crop=faces&fit=crop&w=128&h=128"
                },
                "instagram_username": "cazault",
                "total_collections": 0,
                "total_likes": 0,
                "total_photos": 15,
                "accepted_tos": false,
                "for_hire": false,
                "social": {
                    "instagram_username": "cazault",
                    "portfolio_url": "http://www.davidmenidrey.com",
                    "twitter_username": "cazault",
                    "paypal_email": null
                }
            },
            "tags": []
        },
```

## Använda detta

Eftersom detta response är sparar i `src/_data` så kan vi använda det i våra 11ty filer. Detta finns tillgängligt med som en variabel med samma namn som filen. I detta fall `unsplash`.

För att dumpa datan så att den skrivs ut.

```html
{% for item in unsplash.results %}
    <pre>{{ item | dump(2) }}</pre>
{% endfor %}
```

Vi kan nu använda detta i våra 11ty filer. I detta fall så skriver vi ut en bild från unsplash.

```html
{% for item in unsplash.results %}
    <img src="{{ item.urls.small }}" alt="{{ item.alt_description }}">
{% endfor %}
```

### Problem

Om vi gör på det här sättet så skickar vi requests till Unsplash varenda gång vi laddar sidan. Det gör varken Unsplash eller våra användare glada. Ska vi vara noga är det inte så bra för miljön heller.

### Ett steg på vägen

Vi kan använda [11tys fetch plugin](https://www.11ty.dev/docs/plugins/fetch/) för att cacha data. Det gör att vi bara skickar requests till Unsplash när vi behöver uppdatera datan. Detta gör att vi inte behöver skicka requests till Unsplash varje gång vi laddar sidan. Men detta gäller den request som skickades till Unsplash API, inte varenda bild.

*När du använder fetch pluginet så kom ihåg att lägga till .cache i din .gitignore*

### En bättre lösning

Är att använda [11tys image plugin](https://www.11ty.dev/docs/plugins/image/) och låta 11ty hantera bilderna. Detta gör att vi inte behöver skicka requests till Unsplash varje gång vi laddar sidan eftersom 11tys image plugin cachar bilderna med fetch pluginet åt oss.

För att göra det så behöver vi använda Nunjucks asyncAll loop, eftersom requestsen till image pluginet är asynkrona.

```html
{% asyncAll %}
    {% for item in unsplash.results %}
        {% image item.urls.small, item.alt_description %}
    {% endfor %}
{% endall %}
```

## Bilder

Woohoo vi har bilder. Nu är det ditt jobb att använda CSS grid för att skapa ett bildgalleri.

Se förra veckans lektion om [CSS-grid](https://gist.github.com/jensnti/3af4a838de1abbb612a55d0cd41948a4).

### Temat och färger

Min sökning är på Halloween konstigt nog... Så det sätter temat.
Vi kan utvinna färger ut en av bilderna att använda för att skapa en palett eller bara söka efter en.

https://coolors.co/palettes/popular/halloween

https://coolors.co/44355b-31263e-221e22-eca72c-ee5622

Vi kan sedan använda oss av coolors.co export palette och få färgerna i css.

```css
/* CSS HEX */
--english-violet: #44355bff;
--dark-purple: #31263eff;
--raisin-black: #221e22ff;
--marigold: #eca72cff;
--flame: #ee5622ff;
```

#### Font

Vi ska använda oss av en google font. Men eftersom det nyligen har varit lite ledsna röster kring att google trackar folk även på fonttjänsten så tar vi och laddar ned fonten och hostar den själva.

https://fonts.google.com/specimen/IM+Fell+English+SC?query=english

Ladda ned zippen. Packa upp zippen och lägg den i `src/assets/fonts`.

**Glöm inte att lägga till en `addPassthroughCopy('./src/assets')` i `.eleventy.js config.**

Nästa steg är att ladda in fonten från vår sass fil.

```css
@font-face {
    font-family: 'IM Fell English SC';
    font-style: normal;
    font-weight: 400;
    font-display: swap;
    src: local('IM Fell English SC Regular'), local('IMFellEnglishSC-Regular'), url(/assets/fonts/IMFellEnglishSC-Regular.ttf) format("truetype");
}
```

Sedan kan vi använda den som rubriker på sidan. Jag lämnar det upp till dig att hitta [en annan passande font](https://fontjoy.com/) att använda för brödtext.

På tal om fonter, ett fantastiskt verktyg för att bestämma fontstorlekar är [Utopia](https://utopia.fyi/type/calculator/)

Den låter oss generera en fontscala (eller måttskala vi kan använda) på hela vår sida. Detta är default output med clamp, redo att klistras in och användas i din CSS.

```css
/* @link https://utopia.fyi/type/calculator?c=320,21,1.2,1140,24,1.25,5,2,&s=0.75|0.5|0.25,1.5|2|3|4|6,s-l */

:root {
  --step--2: clamp(0.91rem, calc(0.89rem + 0.10vw), 0.96rem);
  --step--1: clamp(1.09rem, calc(1.05rem + 0.21vw), 1.20rem);
  --step-0: clamp(1.31rem, calc(1.24rem + 0.37vw), 1.50rem);
  --step-1: clamp(1.58rem, calc(1.46rem + 0.59vw), 1.88rem);
  --step-2: clamp(1.89rem, calc(1.71rem + 0.89vw), 2.34rem);
  --step-3: clamp(2.27rem, calc(2.01rem + 1.29vw), 2.93rem);
  --step-4: clamp(2.72rem, calc(2.36rem + 1.83vw), 3.66rem);
  --step-5: clamp(3.27rem, calc(2.75rem + 2.56vw), 4.58rem);
}
```

## css :root

Vad är då `:root`? Det är en pseudo klass som används för att referera till root elementet i en dokumentträd. Det är ett sätt att referera till `html` elementet. Detta är ett bra sätt att definiera globala variabler i CSS.

[Läs mer](https://developer.mozilla.org/en-US/docs/Web/CSS/:root).

## Bygg

Lägg nu till fägerna och skalan i `:root` så kan dy sedan använda dem i din CSS.

```css
.display-header {
    font-family: 'IM Fell English SC', serif;
    font-size: var(--step-4);
    color: var(--english-violet);
}
```

## Data från API

Det här repot innehåller även ett exempel på att hämta data med 11ty fetch från GitHub API.

För att göra det så används fetch för att hämta din user profil från github. Men just användarnamnet är angivet i en speciell fil som heter `.env`. Du kan se en kopia av den filen utan känslig data i `.env-example`.

[dotenv](https://www.npmjs.com/package/dotenv) filer används av ett npm-paket med samma namn. Det är ett sätt att spara känslig data utan att dela den, **eftersom du inte delar den**. Den är bara tillgänglig lokalt på din dator. Men det förutsätter att du har en `.gitignore` fil som säger åt git att ignorera den filen.

```bash
# .gitignore
.env
```

För att då den som använder repot ska veta vilka variabler som behöver anges så skapas då oftast en kopia av filen utan känslig data. Den kallas då `.env-example` och innehåller bara exempel på hur filen ska se ut.
