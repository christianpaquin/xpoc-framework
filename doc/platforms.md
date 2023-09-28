# Platform guidelines

The Cross-Platform Origin of Content (XPOC) framework is platform agnostic. In order to improve interoperability however, it is RECOMMENDED to follow these guidelines when creating entries in a manifest or adding XPOC URIs on the following platforms. 

## YouTube

### Manifest content

-   properties shared by `accounts` and `content`:
    -   `platform`: `YouTube`
    -   `account`: the owner's account name `<accountname>` (without the `@`)
-   `accounts` properties:
    -   `url`: `https://www.youtube.com/@<accountname>/about`
-   `content` properties:
    -   `url`: `https://www.youtube.com/watch?v=<videoID>`
    -   `puid`: `<videoID>`
    -   `timestamp`: exact creation time in  ISO 8601 date-time format (YYYY-MM-DDTHH:MM:SSZ) in UTC. The time can be 00:00:00Z since YouTube only presents the date in its metadata.

### XPOC URI placement

-    On the account page: in the About page's description.
-    On a video content page: in the video's description.

## X/Twitter

It is RECOMMENDED to only list X/Twitter accounts and not individual pieces of content (tweets) in the XPOC manifest. The owner can simply comment on a tweet to add a XPOC URI.

### Manifest content

-   properties shared by `accounts` and `content`:
    -   `platform`: "X"
    -   `account`: the owner's account name `<accountname>` (without the `@`)
-   `accounts` properties:
    -   `url`: `https://twitter.com/<accountname>`
-   `content` properties:
    -   `url`: `https://twitter.com/<accountname>/status/<statusID>`
    -   `puid`: the `<statusID>` from the `url`
    -   `timestamp`: exact creation time in  ISO 8601 date-time format (YYYY-MM-DDTHH:MM:SSZ) in UTC.

### XPOC URI placement

-    On the account page: in the account page's Bio field. Note that a user's bio might appear in a side bar on the site (e.g., a "Relevant people" box), so validation tools should be aware that XPOC URIs might be displayed on a feed page but the corresponding manifest would list the person's account page. 
-    For a Tweet: in a post's or comment's text field.

## Facebook

It is RECOMMENDED to only list Facebook accounts and not individual pieces of content (posts/photos/videos/reels) in the XPOC manifest.

### Manifest content

-   properties shared by `accounts` and `content`:
    -   `platform`: "Facebook"
    -   `account`: the owner's account name `<accountname>`
-   `accounts` properties:
    -   `url`: `https://www.facebook.com/<accountname>`
-   `content` properties:
    -   `url`: it is preferred to list the canonical `https://www.facebook.com/<accountname>/<posts|photos|videos|reels>/<fbid>` URL
    -   `puid`: the Facebook ID `<fbid>` of the item
    -   `timestamp`: exact creation time in  ISO 8601 date-time format (YYYY-MM-DDTHH:MM:SSZ) in UTC.

### XPOC URI placement

-    On the account page: in the account page's Intro field.
-    For a post: in a post's text field.

## Instagram

It is RECOMMENDED to only list Instagram accounts and not individual pieces of content (posts/reels) in the XPOC manifest.

### Manifest content

-   properties shared by `accounts` and `content`:
    -   `platform`: "Instagram"
    -   `account`: the owner's account name `<accountname>`
-   `accounts` properties:
    -   `url`: `https://www.instagram.com/<accountname>/`
-   `content` properties:
    -   `url`: it is preferred to list the canonical `https://www.instagram.com/<p|reel>/<id>/` form
    -   `puid`: the `<id>` from the `url`
    -   `timestamp`: exact creation time in  ISO 8601 date-time format (YYYY-MM-DDTHH:MM:SSZ) in UTC.

### XPOC URI placement

-    On the account page: in the account page's Bio field.
-    For a post: in a post's caption field.

## Medium

Medium accounts and specific stories can be added to a XPOC manifest.

### Manifest content

-   properties shared by `accounts` and `content`:
    -   `platform`: "Medium"
    -   `account`: the owner's account name `<accountname>` (without the `@`)
-   `accounts` properties:
    -   `url`: either the default `https://medium.com/@<accountname>/` form or the subdomain `https://<accountname>.medium.com` form (depending on the owner's account settings).
-   `content` properties:
    -   `url`: either the default `https://medium.com/@<accountname>/<title>-<id>` form or the subdomain `https://<accountname>.medium.com/<title>-<id>` form (depending on the account setting). This is preferred over using the `https://medium.com/p/<id>` short form; these can be used for unlisted stories.
    -   `puid`: the `<id>` from the `url`
    -   `timestamp`: exact creation time in  ISO 8601 date-time format (YYYY-MM-DDTHH:MM:SSZ) in UTC.

### XPOC URI placement

-    On the account page: preferably in the account page's Bio field, optionally in the about page's description.
-    For a story: in the story's body, either at the top or the end.

## TikTok

It is RECOMMENDED to only list TikTok accounts and not individual pieces of content (videos) in the XPOC manifest.

### Manifest content

-   properties shared by `accounts` and `content`:
    -   `platform`: "TikTok"
    -   `account`: the owner's account name `<accountname>`
-   `accounts` properties:
    -   `url`: `https://www.tiktok.com/@<accountname>`
-   `content` properties:
    -   `url`: `https://www.tiktok.com/@<accountname>/video/<id>`
    -   `puid`: the `<id>` from the `url`
    -   `timestamp`: exact creation time in ISO 8601 date-time format (YYYY-MM-DDTHH:MM:SSZ) in UTC.

### XPOC URI placement

-    On the account page: in the account page's Bio field.
-    For a video: in a video's caption field.
