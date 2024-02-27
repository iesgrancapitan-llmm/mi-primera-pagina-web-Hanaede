# UD5 A Validación XSD. Expresiones regulares en la faceta xs:pattern

XML Schema permite definir **restricciones** a los posibles valores de los tipos de datos. Dichas restricciones se pueden establecer en diferentes aspectos, llamados facetas.

Las **facetas** permiten definir restricciones sobre los posibles valores de atributos o elementos. Una de las facetas que pueden utilizarse son los patrones.
```
xs:pattern	
```
Sirve para definir un **patrón** de caracteres admitidos. El valor del patrón tiene que ser una expresión regular.


Una **expresión regular** o regex es una secuencia de caracteres que conforma un patrón de búsqueda. Se utilizan principalmente para la búsqueda de patrones de cadenas de caracteres u operaciones de sustituciones.

Para poder utilizar las expresiones regulares al programar es necesario tener acceso a un **motor de búsqueda** con la capacidad de utilizarlas. 

## Entrega:

Debes generar las siguientes [expresiones regulares](./expresiones-regulares.xml):
- DNI: 12345678Z, 12345678z, 12345678 Z, 12345678-Z
- [Matrícula](https://es.wikipedia.org/wiki/Matr%C3%ADculas_automovil%C3%ADsticas_de_Espa%C3%B1a): 1234 BCD, 5678 ZYX
  - 1234 ABC (inválida, contiene vocal), 1234 QBC (inválida, contiene la Q), 1234 MNÑ (inválida, contiene la Ñ)
- Dirección MAC: AB-CD-F1-23-45-67 (válida), AB:CD:F1:23:45:67 (válida), ABCDF1234567 (válida), AB:CDF1:23:45-67 (inválida)
- Dirección IP: 0.0.0.0 (válido), 14.255.1.2 (válido), 09.1.2.3 (inválido), 1.260.4.5 (inválido), 09.6.5.4 (inválido), 1.2.3.011 (inválido), 
- Número de dos decimales máximo

Para comprobarlas, escribe tanto el fichero [.xml](./expresiones-regulares.xml) como el [.xsd](./expresiones-regulares.xsd) que las valide. Utiliza la clonación y definición de tipos personalizados.

De interés:
- https://www.abrirllave.com/xsd/restricciones.php
- https://regexr.com/
