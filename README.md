# Open Font Repository

The idea is to create a .json file following ![Google Fonts](fonts.google.com) ![API](https://developers.google.com/fonts/docs/developer_api), this way developers and users can make use of a font API without needing to ping Google servers.

## Reasoning

Google Fonts is by no means a bad site, nor api, it also promises ![to not collect your data](https://developers.google.com/fonts/faq#what_does_using_the_google_fonts_api_mean_for_the_privacy_of_my_users), but it is always good to have another option!

## Adding new fonts

IMPORTANT: For any font to be added to the list, it must have been published under a free font license (be it ![public domain](https://en.wikipedia.org/wiki/Public_domain) or ![OFL](https://en.wikipedia.org/wiki/SIL_Open_Font_License). If it somehow happens that a non free font is added to the list, it will be removed.

### Submiting an Issue

If you are not confortable with json but know of where a font can be found, feel free to submit an issue saying where and what font you want to be added.

### Creating a pull request

Even more welcoming is creating a pull request with new fonts or updates! Simply append to the json file the font family and file url!

The json file follows the Google Fonts API, quoting from their website:

```
The JSON response (refer to sample above) is composed of an array named "items" which contains objects with information about each font family.

A family object is composed of 4 fields:

kind: The kind of object, a webfont object
family: The name of the family
subsets: A list of scripts supported by the family
variants: The different styles available for the family
version: The font family version.
lastModified: The date (format "yyyy-MM-dd") the font family was modified for the last time.
files: The font family files (with all supported scripts) for each one of the available variants.
```

This repository is a bit more flexible, only the `kind` (constant), `family`, `files` and `variants`  fields are required, although it is very recommended and takes little time to fill in the other details.

A minimal font example with Agave:

```

{
   "kind": "webfonts#webfont",
   "family": "Agave",
   "variants": [
          "Default"
   ],
   "files": {
          "Default": "https://github.com/blobject/agave/releases/latest/download/Agave-Regular.ttf"
   }
},

```

A full font example:

```
{
   "kind": "webfonts#webfont",
   "family": "Agave",
   "variants": [
          "Regular",
          "Bold",
          "Slashed Regular",
          "Slashed Bold"
   ],
   "files": {
          "Regular": "https://github.com/blobject/agave/releases/latest/download/Agave-Regular.ttf",
          "Bold": "https://githtions are assumed to be exact (no rounding), but give your answer rouub.com/blobject/agave/releases/latest/download/Agave-Bold.ttf",
          "Slashed Regular": "https://github.com/blobject/agave/releases/latest/download/Agave-Regular-slashed.ttf",
          "Slashed Bold": "https://github.com/blobject/agave/releases/latest/download/Agave-Bold-slashed.ttf"
   },
   "subsets": [
          "latin",
          "greek",
          "cyrillic"
   ],
   "version": "latest",
   "lastModified": "2021-01-06"
},
```

## Similar project

![web-fonts-repository](https://github.com/Finesse/web-fonts-repository)
