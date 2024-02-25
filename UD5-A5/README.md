# UD5 A5. Validación. Conceptos

1. **Indica con una X las afirmaciones verdaderas:**

- [ ] Los DTDs son más ricos y poderosos que los XML Schemas

- [] Los DTDs están escritos de acuerdo a la sintaxis XML

- [X] XML Schemas soportan tipos de datos

- [X] XML Schemas soportan namespaces
- [ ] XML Schemas tienen el nodo raíz schema con la URL que contiene la definición de todos los elementos y atributos que se pueden utilizar en un esquema. Eso quiere decir que para programar en XML se necesita estar conectado a Internet.
- [X] En XSD, el atributo xmlns crea un espacio de nombres para cada URL referenciada. Así si hubiese dos elementos con el mismo nombre se diferencian claramente.



2. A continuación aparece la declaración de un esquema XSD. Indica los siguientes elementos:

- prólogo. Define la versión del lenguaje XML y el juego de caracteres utilizado
```
<?xml version="1.0" encoding="UTF-8"?>
```
- prefijo del espacio de nombres (opcional)
```
XS
```
- espacio de nombres XMLSchema
```
xmlns:xs="http://www.w3.org/2001/XMLSchema"
```
```xml
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema
    xmlns:xs="http://www.w3.org/2001/XMLSchema">
		...
<xs:schema />
```
1. A continuación aparece la vinculación de un esquema a un documento XML. Indica (con una X) si está en nuestro sistema de ficheros local o es un esquema público.

- [x] esquema local

- [ ] esquema público
```xml
<factura num="num_fact_1234"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:noNamespaceSchemaLocation="factura.xsd">
	...
</factura>
```

- [ ] esquema local

- [x] esquema público
```xml
<factura num="num_fact_1234"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.miempresa.com/factura.xsd">
...
</factura>	
```
  
5. De los siguientes tipos predefinidos por el espacio de nombres XMLSchema del W3C, marca con una X los numéricos:
- [ ] normalizedString
- [ ] dateTimeStamp
- [ ] language
- [ ] IDREFS
- [ ] dayTimeDuration
- [ ] NMTOKEN
- [ ] NMTOKENS
- [ ] Name
- [ ] NCName
- [ ] ID
- [ ] IDREF
- [ ] ENTITY
- [x] integer
- [ ] yearMonthDuration
- [x] nonPositiveInteger
- [x] negativeInteger
- [x] long
- [x] int
- [x] short
- [x] byte
- [ ] token
- [x] nonNegativeInteger
- [x] unsignedLong
- [x] unsignedInt
- [ ] ENTITIES
- [x] unsignedShort
- [x] unsignedByte
- [x] positiveInteger

6. Adjunta un fichero .xsd con el siguiente diseño:
```xml
<!-- definición de elementos simples -->
<!-- definición de atributos -->
<!-- definición de elementos  complejos -->
<!-- definición de los tipos simples -->
<!-- definición de los tipos complejos -->
<!-- elemento raíz -->
```
[Archivo xsd](./actividad6.xsd)

7. Con respecto a la validación con XSD indica:
- Un esquema es un documento *XML* al que se le coloca la extensión **.xsd** . Al ser un archivo XML tiene la estructura habitual de todo documento XML con la obligación de que el elemento **raíz** se llame **<xsd:schema>** .
- Etiqueta que identifica la raíz de un documento XML Schema:  
  **<xs:schema> **  

- Etiquetas que identifican las partes de un esquema:
  - Elementos, definidos con etiquetas **<xs:element>**. Para indicar los elementos permitidos en los documentos que sigan el esquema.
  - Atributos, etiqueta **<xs:attribute>**.
  - Tipos simples, que permiten definir los tipos simples de datos que podrá utilizar el documento XML. Lo hace la etiqueta **<xs:simpleType>** .
  - Tipos complejos, mediante la etiqueta **<xs:complexType>**
  - Documentación, información utilizable por aplicaciones que manejen los esquemas. Etiquetas **<xs:annotation>** y **<xs:documentation>**.
- Componentes locales y globales en un esquema:
  - En ámbito **global**. Se trata de los elementos del esquema que se coloquen dentro de la etiqueta raíz schema y que no están dentro de ninguna otra. Estos elementos se pueden utilizar en cualquier parte del esquema.
  - En ámbito **local** . Se trata de elementos definidos dentro de otros elementos. En ese caso se pueden utilizar sólo dentro del elemento en el que están inmersos y no en todo el documento. Es decir si, por ejemplo, si dentro de la definición de un atributo colocamos la definición de un tipo de datos, este tipo de datos sólo se puede utilizar dentro del elemento xs:attribute en el que se encuentra la definición del tipo de datos.
- Dentro de la etiqueta xs:element, indica:
  - atributos obligatorios:
    - name: Este atributo especifica el nombre del elemento. Es obligatorio y debe ser único dentro del ámbito del esquema.
  - atributos optativos:
    - type: Este atributo especifica el tipo de datos del elemento.
  - ref: Este atributo hace referencia a otro elemento definido en el esquema.
  - minOccurs: Este atributo especifica el número mínimo de veces que el elemento puede aparecer en el documento XML. Por defecto, su valor es 1.
  - maxOccurs: Este atributo especifica el número máximo de veces que el elemento puede aparecer en el documento XML. Por defecto, su valor es 1.
  - abstract: Este atributo indica si el elemento es abstracto o no. Su valor puede ser "true" o "false". Por defecto, su valor es "false".
   - nillable: Este atributo indica si el elemento puede tener el atributo xsi:nil establecido en "true" en un documento XML. Su valor puede ser "true" o "false". Por defecto, su valor es "false".

8. Definición de un elemento vacío en XSD
- Un elemento vacío se define utilizando la etiqueta <xs:element> sin incluir ninguna definición de contenido dentro de ella. Ejemplo:  
  
`<xs:element name="elementoVacio"/>`

De interés
- https://jorgesanchez.net/manuales/xml/xml-validacion.html
- https://www.w3schools.com/xml/el_restriction.asp
- https://lm-xml-apuntes.readthedocs.io/apuntes/40_esquemas_xml.html#tipos-de-elementos
