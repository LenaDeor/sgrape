# Sgrape 🍇

Build and maintain simple webscrapers easily.

# Install

```

$ npm i sgrape

```

# Usage

```

const Sgrape = require('sgrape');

const schema = {
  startPage: 'https://www.website.com/page',
  selector: '.element-selector',
  nextPageSelector: '.page-link[rel=next]', // optional
  title: { selector: 'h1', attr: 'text' },
  link: { selector: 'a.title', attr: 'href' },
  desc: { selector: 'p.desc', attr: 'text' },
};

// per field helpers (optional)
const helpers = {
  title: title => title.replace('/', ' '),
  desc : desc => desc.substr(0,30) + '...'
};

const scraperConfig = { schema, helpers };

// executes once job finished.
scraperConfig.done = res => {
  // insert res to db or whatever
  console.log(res);
};

const scraper = new Sgrape(scraperConfig);

```

# Versioning

Sgrape uses [SemVer](http://semver.org/) for versioning.

# License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT)

```

```
