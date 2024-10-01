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


