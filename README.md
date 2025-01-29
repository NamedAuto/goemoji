# goemoji

Simple go map containing the emoji character as the key and formatted as seen below

```go
// Map
var EmojiMap = map[string]Emoji{}

type Emoji struct {
    Slug        string    `json:"slug"`
    Character   string    `json:"character"`
    UnicodeName string    `json:"unicodeName"`
    CodePoint   string    `json:"codePoint"`
    Group       string    `json:"group"`
    SubGroup    string    `json:"subGroup"`
    Variants    []Variant `json:"variants,omitempty"`
}
```

and emojis look like this in the map

```go
"🚂": {
    Slug:        "e1-0-locomotive",
    Character:   "🚂",
    UnicodeName: "E1.0 locomotive",
    CodePoint:   "1F682",
    Group:       "travel-places",
    SubGroup:    "transport-ground",
},
```

While monochrome versiosn are not considered emoji, they are also included
as seen below

```go
"☠️": {
    Slug:        "e1-0-skull-and-crossbones",
    Character:   "☠️",
    UnicodeName: "E1.0 skull and crossbones",
    CodePoint:   "2620 FE0F",
    Group:       "smileys-emotion",
    SubGroup:    "face-negative",
},
"☠": {
    Slug:        "e1-0-skull-and-crossbones-text",
    Character:   "☠",
    UnicodeName: "E1.0 skull and crossbones (text)",
    CodePoint:   "2620",
    Group:       "smileys-emotion",
    SubGroup:    "face-negative",
},
```

Variants of an emoji like below are given the same Group and SubGroup as the parent emoji

```go
"👋": {
    Slug:        "e0-6-waving-hand",
    Character:   "👋",
    UnicodeName: "E0.6 waving hand",
    CodePoint:   "1F44B",
    Group:       "people-body",
    SubGroup:    "hand-fingers-open",
},
"👋🏻": {
    Slug:        "E1-0-waving-hand-light-skin-tone",
    Character:   "👋🏻",
    UnicodeName: "E1.0 waving hand light skin tone",
    CodePoint:   "1F44B 1F3FB",
    Group:       "people-body",
    SubGroup:    "hand-fingers-open",
}
```

Emoji data was retrieved from <https://emoji-api.com>  
current unicode version: 15  
last update: August 2023
