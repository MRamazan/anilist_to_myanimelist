## Data
anilist_to_mal.json is basically a dictionary. Keys are basically anime title.
Every value of the key has anilist id and myanimelist id information in it. 
Dictionary is consisted of total 17143 anime. There are 17029 anime with unique title and 114 anime with same title and different ids.
I structured this JSON dictionary in a somewhat complex way due to the specific requirements of my project.  
It doesn't include all the anime listed on AniList—only those that have received at least 100 user reviews in my dataset of 148 million user reviews.

Every value of a key is dictionary, if there are more than one anime with same title, there is an extra key named "datas" in the value dictionary.

### Example of a anime with unique title
```
"Air Gear": {
        "mal_id": 857,
        "title": {
            "romaji": "Air Gear",
            "english": "Air Gear",
            "native": "エア・ギア"
        },
        "anilist_id": 857,
        "episodes": 25
    }
```

### Example of anime with common title
```
"Uchuu Kaizoku Captain Harlock": {
        "mal_ids": [],
        "episodes": [
            1,
            42
        ],
        "datas": [
            {
                "mal_id": 17269,
                "title": {
                    "romaji": "Uchuu Kaizoku Captain Harlock",
                    "english": "Harlock: Space Pirate",
                    "native": "宇宙海賊キャプテンハーロック"
                },
                "anilist_id": 17269,
                "episodes": 1
            },
            {
                "mal_id": 1000,
                "title": {
                    "romaji": "Uchuu Kaizoku Captain Harlock",
                    "english": "Captain Harlock Space Pirate",
                    "native": "宇宙海賊キャプテンハーロック"
                },
                "anilist_id": 1000,
                "episodes": 42
            }
        ]
    }
```

