# Crystal Lang Polylines


[![Release](https://img.shields.io/github/release/BuonOmo/polylines.svg)](https://github.com/BuonOmo/polylines/releases)
[![Build Status](https://travis-ci.org/BuonOmo/polylines.svg?branch=master)](https://travis-ci.org/BuonOmo/polylines)
[![Docs](https://img.shields.io/badge/docs-available-brightgreen.svg)](https://buonomo.github.io/polylines/)


A Crystal implementation of the [Google polyline algorithm](https://code.google.com/apis/maps/documentation/utilities/polylinealgorithm.html).

Greatly inspired by the Ruby implementation [fast-polylines](https://github.com/klaxit/fast-polylines), it is mostly
existing for performance comparison between Ruby C extensions and Crystal!

If you are curious: encoding is slower in crystal, but decoding is roughly the same.
If you are even more curious, `make benchmark` here and in [fast-polylines](https://github.com/klaxit/fast-polylines) 😉.
With a MacBook pro 1,4 GHz i5, here's the result:

```text
——————————————————————————————— ENCODING ————————————————————————————————

CrystalPolylines 145.17k (  6.89µs) (± 3.53%)  14.2kB/op  fastest

———————————————————————————————  DECODING ————————————————————————————————

CrystalPolylines   1.32M (756.06ns) (± 3.74%)  1.62kB/op  fastest
```

## Installation

Add the dependency to your `shard.yml`:

```yaml
dependencies:
  polylines:
    github: BuonOmo/polylines
```

Run `shards install`

## Usage

```crystal
require "polylines"

# Polylines.encode(array, precision = 5)
Polylines.encode([[38.5, -120.2], [40.7, -120.95], [43.252, -126.453]])
# Polylines.decode(polyline, precision = 5)
Polylines.decode("_p~iF~ps|U_ulLnnqC_mqNvxq`@")

Polylines.encode([[12.1232493, 2.9481493], [13.8474392, 16.8373924]], 7)
```

## Contributing

1. Fork it ([BuonOmo/polylines/fork](https://github.com/BuonOmo/polylines/fork))
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
