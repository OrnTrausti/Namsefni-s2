---

### Verkefni 3
- Lykilmatsverkefni
- 30% af heildareinkunn
- Viðfangsefni:
  - Notkun á [JSON](https://en.wikipedia.org/wiki/JSON) og [API](https://en.wikipedia.org/wiki/API_key)
  - Jinja Template: inheritance, skilyrði
  - Eigið CSS Responsive Grid Layout eða PureCSS 
  - 

---

### Verkefnalýsing
 
1. Útfærðu vefforrit í Flask sem nýtir API.
1. Notum [The Movie Database API](https://developers.themoviedb.org/3/getting-started/introduction)  
1. Nemendur þurfa að skrá sig inn á síðuna hér að ofan og sækja um **_API key_**.  Það kostar ekkert að skrá sig. [TMDB - Sign up](https://www.themoviedb.org/signup)
1. Á forsíðu (index) skal birta grunn upplýsingar um 20 random bíómyndir.  Birta skal amk nafn og mynd.
1. Ef valin er ein bíómynd af forsíðu er farið á undirsíðu sem birtir nánari upplýsingar um valda bíómynd.
1. **Engin harðkóðun** til að standast grunnkröfur.
1. Byrjið á því að útfæra grunnkröfur til að standast lykilmat, síðan skulu þið bæta við virkni / útlit til að hækka einkunn.
1. Hér fyrir neðan er nánari útlistun á þeim þáttum sem þarf að uppfylla til að fá tiltekna einkunn.


**Ath:** Ekki setja inn persónuupplýsingar, sumir API biðja um að fá kreditkorta upplýsingar (sleppa þeim).<br>

---
### Námsmat

- Forsíða birtir 20 bíómyndir með nafni (_original-title_) og mynd (_poster-path_) bíómyndar (_static route_) þegar semllt er á mynd birtist undirsíða
- Undirsíða birtir nánari upplýsingar um valda bíómynd (_dynamic route_)
    - nafn bíómyndar (_original-title_)
    - mynd (_poster-path_)
    - textalýsing bíómyndar (_overview_)
    - útgáfudagur bíómyndar (_release-date_)
    - lengd bíómyndar (_runtime_)
    - útgáfudagur bíómyndar (_release-date_), dagsetning á íslensku formati
 - Flokkar sem bíómynd tilheyrir (kvikmyndagrein - _movie genre_)
 - Jinja: erfðir, include, lúppur og skilyrði
 - CSS Responsive Grid uppsetning
 - Viðeigandi errorhandler routes    

### Sundurliðun Einkunnar:

- 10
  - Hægt að skoða trailer fyrir valda bíómynd 
  - bætist við einkunn 9
- 9
  - Upplýsingar um helstu leikara og leikstjóra fyrir valda bíómynd ( sigta út, ekki lúppa í gegnum allt "crew" og birta )
  - bætist við einkunn 8
- 8
  - Ef valinn er flokkur (_genre_) í efnisyfirliti (_nav_) opnast síða sem birtir random bíómyndir úr völdum flokk (_dynamic route_)
  - Textalýsing (_overview_) bíómyndar kemur á íslensku ef hún er til, annars á ensku 
  - dagsetning á íslensku formati
  - bætist við einkunn 7 
- 7
  - flokkar sem bíómyndir tilheyra (_genre_) í efnisyfirliti (_nav_)
  - Leikstjóri myndar, texti og ljósmynd
  - bætist við einkunn 6
- 6
  - Undirsíða birtir nánari upplýsingar um valda bíómynd (_dynamic route_)
    - nafn bíómyndar (_original-title_)
    - mynd (_poster-path_)
    - textalýsing bíómyndar (_overview_)
    - útgáfudagur bíómyndar (_release-date_)
    - lengd bíómyndar (_runtime_)

  - Viðeigandi errorhandler routes  
  - Hnökralaus útlitshönnun (eigið CSS eða PureCSS virkar að fullu)  
  - bætist við einkunn 5
- 5
  - forsíða birtir nafn (_original-title_) og mynd (_poster-path_) bíómyndar (_static route_)
  - Jinja: erfðir, innifalið (_include_), lúppur og skilyrði
  - engin harðkóðun í Jinja template
  - Responsive Grid uppsetning í lagi
  - bætist við einkunn 4
- 4
  - forsíða birtir nafn (_original-title_) og mynd (_poster-path_) bíómyndar (_static route_)
  - Undirsíða birtir valda bíómynd
  - Stílsíða virk en hnökrar í útlitshönnun 
  - bætist við einkunn 3
- 3   
  - Jinja ábótavant, vantar erfðir - (_extends_) og/eða  innifalið - (_include_)
  - Vantar stílsíðu eða hún birtist ekki
  - bætist við einkunn 2 
- 2
  - Keyrir en lítil sem engin virkni (_Json_)
- 1
  - Keyrir ekki, stórlega ábótavant
- 0
  - Engu skilað
  - **Eins lausnir hjá tveimur eða fleiri nemendum**


### Verkefnaskil

- Skilaðu verkefni 3 í eigin verkefnageymslu (_repository_) 
- Ekki skila **venv** umsjónarkerfinu í verkefnageymsluna notið  **.gitignore** til að koma í veg fyrir það

---

### Dæmi um gögn
Hlekkurinn / API endpoint [https://api.themoviedb.org/3/movie/550?api_key=???](https://api.themoviedb.org/3/movie/550?api_key=???) skilar okkur upplýsingum um bíómynd eftir id:  Í þessu tilviki bíómyndin The Fight Club sem hefur id = 550.  Í staðinn fyrir ??? setur þú þinn API key.
```python

{
  "adult": false,
  "backdrop_path": "/fCayJrkfRaCRCTh8GqN30f8oyQF.jpg",
  "belongs_to_collection": null,
  "budget": 63000000,
  "genres": [
    {
      "id": 18,
      "name": "Drama"
    }
  ],
  "homepage": "",
  "id": 550,
  "imdb_id": "tt0137523",
  "original_language": "en",
  "original_title": "Fight Club",
  "overview": "A ticking-time-bomb insomniac and a slippery soap salesman channel primal male aggression into a shocking new form of therapy. Their concept catches on, with underground \"fight clubs\" forming in every town, until an eccentric gets in the way and ignites an out-of-control spiral toward oblivion.",
  "popularity": 0.5,
  "poster_path": null,
  "production_companies": [
    {
      "id": 508,
      "logo_path": "/7PzJdsLGlR7oW4J0J5Xcd0pHGRg.png",
      "name": "Regency Enterprises",
      "origin_country": "US"
    },
    {
      "id": 711,
      "logo_path": null,
      "name": "Fox 2000 Pictures",
      "origin_country": ""
    },
    {
      "id": 20555,
      "logo_path": null,
      "name": "Taurus Film",
      "origin_country": ""
    },
    {
      "id": 54050,
      "logo_path": null,
      "name": "Linson Films",
      "origin_country": ""
    },
    {
      "id": 54051,
      "logo_path": null,
      "name": "Atman Entertainment",
      "origin_country": ""
    },
    {
      "id": 54052,
      "logo_path": null,
      "name": "Knickerbocker Films",
      "origin_country": ""
    },
    {
      "id": 25,
      "logo_path": "/qZCc1lty5FzX30aOCVRBLzaVmcp.png",
      "name": "20th Century Fox",
      "origin_country": "US"
    }
  ],
  "production_countries": [
    {
      "iso_3166_1": "US",
      "name": "United States of America"
    }
  ],
  "release_date": "1999-10-12",
  "revenue": 100853753,
  "runtime": 139,
  "spoken_languages": [
    {
      "iso_639_1": "en",
      "name": "English"
    }
  ],
  "status": "Released",
  "tagline": "How much can you know about yourself if you've never been in a fight?",
  "title": "Fight Club",
  "video": false,
  "vote_average": 7.8,
  "vote_count": 3439
}
```
