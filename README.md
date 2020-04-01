# Datenaustausch zwischen Postgres und ISYBAU

## Import:

    ogr2ogr -f PostgreSQL PG:"host=127.0.0.1 port=port dbname=isybau password=xxxxxxxxx user=postgres schemas=isybau" GMLAS:Isybau2013-geom2.xml -oo XSD=1302_ISYBAU_XML_Schema\1302-metadaten.xsd -oo EXPOSE_METADATA_LAYERS=YES -forceNullable

## Export:

    ogr2ogr -f GMLAS pgsql-export.xml PG:"host=127.0.0.1 port=port dbname=isybau password=xxxxxxxxx user=postgres schemas=isybau"

nach dem Export sind folgende Ersetzungen durchzuführen:

 - isy:     => löschen
 - xsi:nil="true"     => löschen
 - false    => 0
 - </Datenkollektive>\r\n<Datenkollektive>    => löschen
 - </Geometriedaten>\r\n<Geometriedaten>    => löschen
 - </Knoten>\r\n<Knoten>    => löschen
 - Kopfzeile austauschen


# isybau2qgep

Instructions on using the [OGR GMLAS driver](http://www.gdal.org/drv_gmlas.html) for the (german specific) wastewater data format ["ISYBAU Austauschformate Abwasser (XML)"](http://www.arbeitshilfen-abwasser.de/html/A7ISYBAU_ATF_XML.html) in [QGIS](https://qgis.org) and the QGIS based waste-water application [QGEP](https://github.com/QGEP/QGEP).

_For descriptions and backgrund please see the [Wiki!](https://github.com/tschuettenberg/isybau2qgep/wiki) (in german)_

***

[Anleitung](https://github.com/tschuettenberg/isybau2qgep/wiki) für die Verwendung des [OGR GMLAS Treibers](http://www.gdal.org/drv_gmlas.html) für die [ISYBAU Austauschformate Abwasser (XML)](http://www.arbeitshilfen-abwasser.de/html/A7ISYBAU_ATF_XML.html) in [QGIS](https://qgis.org) sowie in Verbindung mit der QGIS-basierten Abwasserfachschale [QGEP](https://github.com/QGEP/QGEP).

_Erläuterungen und Hintergrund im [Wiki!](https://github.com/tschuettenberg/isybau2qgep/wiki)_
