# YouTubeSearch

**Sources**
https://developers.google.com/youtube/v3/docs/search
https://developers.google.com/youtube/v3/guides/implementation/pagination?hl=en

**API Functions**
Search



Search Specifications
- part = "snippet"
- q = "health"
- maxResult = 50
- order = "date"
- type = "video"
- videoCategoryId = "27" # Education ("27"), Science & Technologie ("28"), People & Blogs ("22"), Howto & Style ("26"). Focusing on healt related content, thus exlcuding e.g. News, Comedy... etc as it deviates to other topic clusters (politics, entertainemnt...)
- pageToken = response["nextPageToken"]

Search Output Get
- id.videoId # To specify result search
- snippet.title # Get video title
- snippet.description # Get video description
- snippet.publishedAt # datetime
- snippet.channelTitle

Search Output Layout

{
  "kind": "youtube#searchResult",
  "etag": etag,
  "id": {
    "kind": string,
    "videoId": string,
    "channelId": string,
    "playlistId": string
  },
  "snippet": {
    "publishedAt": datetime,
    "channelId": string,
    "title": string,
    "description": string,
    "thumbnails": {
      (key): {
        "url": string,
        "width": unsigned integer,
        "height": unsigned integer
      }
    },
    "channelTitle": string,
    "liveBroadcastContent": string
  }
}

Was steckt in dem Parameter regioCode = 'US'
Ja, mit "relevant" in Bezug auf den Parameter regionCode ist hauptsächlich gemeint, dass die Videos in der angegebenen Region (in deinem Fall die USA) auf irgendeine Weise für Nutzer in dieser Region wichtig oder populär sind. Relevanz bezieht sich auf verschiedene Faktoren, die auf das Konsumverhalten der Nutzer in dieser Region basieren.

Hier sind die wichtigsten Faktoren, die die Relevanz definieren:
1. Konsumverhalten der Nutzer:

    Wie oft ein Video von Nutzern in dieser Region angeschaut wird.
    Engagement: Videos, die viele Likes, Kommentare und Shares von Nutzern aus der Region bekommen, werden als relevanter eingestuft.
    Suchanfragen: Wenn viele Nutzer in den USA nach bestimmten Themen (z. B. "health advice") suchen, werden Videos, die diese Keywords enthalten, höher priorisiert.

2. Lokale Trends und Empfehlungen:

    Regionale Trends: YouTube berücksichtigt lokale Trends, z. B. welche Videos gerade in einer bestimmten Region viral gehen oder häufig angesehen werden.
    Empfehlungen: YouTube empfiehlt Nutzern in einer Region Inhalte basierend auf den Interessen, die in dieser Region vorherrschen.

3. Beliebtheit:

    Ein Video, das in der USA oft angesehen wird oder auf der Startseite von Nutzern in den USA angezeigt wird, hat eine höhere Wahrscheinlichkeit, in der Suchergebnisseite aufzutauchen, auch wenn es ursprünglich in einem anderen Land hochgeladen wurde.
    Beliebte Videos in der Region werden ebenfalls basierend auf den Interaktionen priorisiert (z. B. Likes, Kommentare, Shares).

4. Sprache und kultureller Kontext:

    Videos in der Sprache, die in der Region am häufigsten gesprochen wird, oder Inhalte, die für die kulturellen Interessen der Region relevant sind, werden ebenfalls als relevanter angesehen.
    Ein Video auf Englisch wird für die USA höher gewichtet als ein Video in einer anderen Sprache, sofern es um gleiche Suchbegriffe geht.


