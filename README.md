# SDLTM Importer

[![Gem Version](https://badge.fury.io/rb/sdltm_importer.svg)](https://badge.fury.io/rb/sdltm_importer) [![Build Status](https://travis-ci.org/diasks2/sdltm_importer.png)](https://travis-ci.org/diasks2/sdltm_importer) [![License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat)](https://github.com/diasks2/sdltm_importer/blob/master/LICENSE.txt)

This gem handles the importing and parsing of .sdltm translation memory files.

## Installation

Add this line to your application's Gemfile:

**Ruby**  
```
gem install sdltm_importer
```

**Ruby on Rails**  
Add this line to your application’s Gemfile:  
```ruby 
gem 'sdltm_importer'
```

## Usage

```ruby
# Get the high level stats of a .sdltm file
file_path = File.expand_path('../sample.sdltm')
sdltm = SdltmImporter::Sdltm.new(file_path: file_path)
sdltm.stats
# => {:tu_count=>1, :seg_count=>2, :language_pairs=>[["en", "fr"]]}

# Extract the segments of a .sdltm file
# Result: [translation_units, segments]
# translation_units = [tu_id, creation_date]
# segments = [tu_id, segment_role, word_count, language, segment_text, creation_date]

sdltm.import
# => [[["6234-1457917153-1"]], [["6234-1457917153-1", "source", 2, "en", "Hello world"], ["6234-1457917153-1", "target", 3, "fr", "Bonjour le monde"]]]
```

## Contributing

1. Fork it ( https://github.com/diasks2/sdltm_importer/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

## License

The MIT License (MIT)

Copyright (c) 2016 Kevin S. Dias

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
