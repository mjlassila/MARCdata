# MARCdata

Writes selected parts of a [MARC XML](http://www.loc.gov/standards/marcxml/) bibliographic data file into a .csv.gz file.

## Preliminaries

+ [GNU Make](http://www.gnu.org/software/make/) (build automation)
+ [Clang](http://clang.llvm.org/) (compiler)
+ [zlib.h](http://www.zlib.net/) (header)

## C++11

Requires standard library support for the following C++11 extensions:

+ range-based for loop
+ *auto* type specifier
+ *nullptr* identifier

## Usage

Input files should be placed in folder 'data'. Output goes there as well.

### ESTC

	make estc
	./estc

### Fennica

	make fennica
	./fennica

### Kungliga

	bash split-kungliga.sh
	make kungliga
	./kungliga

### Göttingen

	make cerl
	./cerl

### Holdings

	Name exported Voyager holdings as holdings.xml.

	Selected fieldset is based on MARC fields used in Jyväskylä University Library holdings records, 
	so your mileage might vary. 

	make holdings
	./holdings

## Author

[Niko Ilomäki](https://github.com/NVI/)

Contributions by 

* [Leo Lahti](https://github.com/antagomir/)
* [Matti Lassila](https://github.com/mjlassila/)


## License

MIT License

[RapidXML](http://rapidxml.sourceforge.net/) library by Marcin Kalicinski and licensed under the MIT License

[Gzstream](http://www.cs.unc.edu/Research/compgeom/gzstream/) library by Deepak Bandyopadhyay and Lutz Kettner and licensed under LGPL 2.1


## Log

Jul 12 Odd behavior in language field (008) parsing was observed with
Kungliga. It turned out that the last digits 38/39 are sometimes
missing in Kungliga 008 field, so the parser was changed to start
reading from the beginning of the line instead of the end of the line
(as in other catalogs). This yields recognizable language codes for
99.88% of the entries now.



