# summa.json
The Summa Theologica by St Thomas Aquinas, parsed to JSON for ease of use. The source version used is the Benziger Bros. edition, 1947.

## JSON Format
All JSON can be found in the [`json` folder](https://github.com/Jacob-Gray/summa.json/tree/master/json).

The Summa is divided up into 7 parts, and the JSON reflects this, dividing each part up into sections, articles, and "other". Whenever the JSON refers to a part, it will use a string such as `FP`.

Each part follows this format:
```js
{
  "title": "Title string",
  "questions": { 
    "1": Page,
    // The key is the ID of the question, repeat for all questions
   },
  "sections": { 
    "1": {
      "id": 1,
      "title": "Section title",
      "part": "FP",
      "questions": {
        "2": Page
        // The key is the ID of the question, repeat for all questions
      }
    }
   },
  "other": { 
    "XP-NOTE": Page
    // The key is the filename for this page, repeat for all non-question pages in this part
   }
}
```

`Page` and `Question` are very similar, being parsed in the same way, but `Page` simply lacks all of the question specific data. `Page` is also quite rare, only being used for Prologue and Editor note pages.


The JS parser and HTML source files can be found at [summa-to-json](https://github.com/Jacob-Gray/summa-to-json), if you are interested in how it functions.
