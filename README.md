# GeoJSON Decimal Clipper

Strips gratuitous decimals from a GeoJSON file. But will work for any text file, really.

```
// original uber precise coords
[-90.3515625,53.73571574532637],[-92.13134765625,53.199451902831555]

// after running, clipped to your liking
[-90.35156,53.73571],[-92.13134,53.19945]
```

**Careful Now**

-   Will affect every decimal number in the file, not just Geometry co-ords
-   Will even update numbers encoded in strings.
-   Does not round. Just drops the offending precision.
-   Untested for anything other than UTF8 text files.

## Command Line

To pull the dependencies

```
npm install
```

To givver

```
npm run start
```

## App Setup

To change the number of decimal values to keep, update the value of `MAX_DECIMAL` in `index.ts`.

To change the file to process, update the parameter of the very last line of `index.ts`.

```
parser('./localFolder/myfile.json');
```

The processed file will be written in the same location, with filename `origfilename.squash.json`.

## Testing

Works on my machine.
