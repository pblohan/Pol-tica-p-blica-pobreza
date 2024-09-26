# Politica publica de pobreza
This is mi practice case for the certificate of data analysis by coursera, derivated also about my grath hipótesis

## Análisis de dimensiones para políticas públicas de pobreza en latinoamérica

 &nbsp;

## Escenario: formulación e identificación del problema
  Las políticas públicas se diseñan a partir de teorías de cambio que buscan generar resultados específicos, pero es crucial evaluarlas en función de la evidencia disponible. Las políticas públicas basadas en evidencia (PBE) integran datos y conocimiento en su diseño, siendo esenciales para mejorar la efectividad de las intervenciones. Sin embargo, su éxito depende no solo de aspectos técnicos, sino de la capacidad para gestionar sistemas de información complejos y del acceso y uso de la evidencia  por parte de los actores políticos. Un ejemplo destacado es el programa "Medellín Solidaria". La intención del trabajo es identificar cuáles son las dimensiones más relevantes que deben ser tenidas en cuenta para hacer políticas públicas de pobreza y asi mejorar el impacto de las mismas.

## Desarrollo de caso: preparación
Según el BID, la ONU, entre otras fuentes, las dimensiones para mejorar el desarrollo humano se circunscriben en estas: salud, educación, empleo, vivienda, dinámica familiar,
ingresos, acceso material, por lo que la fuente de datos más esencial para hacer este caso de estudio tendría que ser una que tenga este tipo de datos, para ello se eligió usar como base la base de datos de calidad de vida de medellín.

### web scraping
Luego de un rastreo y análisis exploratorio, se decide usar como principal fuente de datos la base de datos de calidad de vida de Medellín como vamos, que dentro de si, contiene datos elementales como: salud, educación, trabajo, vivienda, dinámica familiar,
ingresos, acceso material. además de sectorizarlo según edad, sexo, comuna, entre otros.

([codigo scraping.png](https://github.com/pblohan/Pol-tica-p-blica-pobreza/blob/f6259636c21fefb57d8f4af5ee9cecce90c6989c/codigo%20scraping.png))

## Recopilación y Preparación de Datos:
### 2.1. Fuentes de Datos:
Identificar y descargar datos de libre acceso en
formatos HTML y CSV. En este caso, la fuente principal de datos será la
base de datos proporcionada por la alcaldía “Calidad de vida. Medellín
cómo vamos” en la que se detalla año tras año y comuna tras comuna,
datos específicos relacionados a los sectores sociales: salud,
educación, vivienda y servicios públicos, seguridad, demografía,
pobreza y desigualdad, medio ambiente. Esta base de datos está
sectorizada por comuna y por ciudad dependiendo del indicador, y los
datos van desde el 2004 hasta el 2022 dependiendo igualmente de la
variable.
Por razones practicas, y debido a que los datos no están ajustados de
una manera uniforme, este trabajo también utilizará otras fuentes de
datos abiertos como el DANE y otros instrumentos de medición.

### 2.2. Preprocesamiento:Limpieza de datos:
(i) Manejo de valores faltantes,
eliminación de duplicados, y corrección de errores; (ii) Transformación
de datos: Conversión de datos no estructurados en HTML a formato
tabular si es necesario.
-Organización: En un primer momento la base de datos de “Calidad
de vida. Medellín cómo vamos” preparada para entender la
estructura, medición y tipología de los datos. Es común que en un
inicio los datos estén dispersos y desorganizados, y este caso no era
la excepción. Los principales problemas a los que me enfrenté al
iniciar el proceso de limpieza de datos fueron: los datos estaban
divididos en varios tipos de medición, la escala de abstracción era
diferente dependiendo la variable, la temporalidad en que fueron
medidos no era la misma, y en general estaban organizados de
diferentes maneras que imposibilitaban un análisis que permitiera
comparar dos variables en la misma escala.
Para esto, el primer momento se hizo una gestión de los datos. Se
organizaron en un mapa mental para entender cuál era su estructura,
nomenclatura y dispersión, luego se organizaron en varias matrices
para darles un orden a las variables y posteriormente de manera
manual organizar los datos en una escala de medición similar:
porcentaje, índices y tasas. Luego cuando ya los datos tenían este
orden, se dispusieron en una nueva hoja de cálculo uniforme
organizada desde el 2004 hasta el 2022 y se ordenaron de acuerdo
con la comuna

- Procesamiento: Cuando los datos ya tenían un orden establecido,
era momento de gestionar su integridad, es decir, de manera
manual seguir organizándolos para garantizar que no hubiese
sesgo, que los datos fueran coherentes con la información, que el
margen de error fuese el mínimo posible, en general que el
proceso de transformación de datos sucios a datos limpios fuese
lo más exitoso posible. De esta manera, los datos ubicados en el
dataframe en que se dispusieron en Python ya están listos para
analizarse

([Fase de procesamiento y limpieza de datos](https://github.com/pblohan/Pol-tica-p-blica-pobreza/blob/f6259636c21fefb57d8f4af5ee9cecce90c6989c/codigo%20scraping.png))
La anterior imagen corresponde a todos los datos segmentados por las dimensiones anteriormente descritas, puestos cada uno en una escala de medicióon similar

## Análisis

### 1.Análisis descriptivo: 
Como primer fuente de datos confirmatoria se tomó como referente diversas políticas públicas de pobreza usadas en latinoamérica y se extrajo de las mismas las principales dimensiones que impactaban para el desarrollo humano y por ende, superación de la pobreza

([Análisis confirmatorio](https://github.com/pblohan/Pol-tica-p-blica-pobreza/blob/2cd159a3d2c47a090462667c799bdbcdfae607ca/identificaci%C3%B3n%20de%20dimensiones.png))

## 2. Análisis confirmatorio: 
Luego de confirmar las principales dimensiones, se pretendía no únicamente basarse en lo que los datos de las políticas decían, sino sustentar la hipótesis en datos de carácter más empíricos, más reales, por ello se tomó como referencia los datos relacionados a la base de datos de medellín solidaria y se hizo uso de la técnica de clustering para determinar no solo cuáles dimensiones preponderaban, sino además cómo se configuraban cada una y qué relación significativa tenían con respecto a otras

([Análisis de clustering](https://github.com/pblohan/Pol-tica-p-blica-pobreza/blob/2cd159a3d2c47a090462667c799bdbcdfae607ca/fase%20de%20an%C3%A1lisis.png))
Lo que se pudo encontrar fueron 4 grupos principalmente, en los cuales, las dimensiones más fuertes efectivamente eran la salud, educación, empleo. Pero junto a ellas, otras dimensiones elementales que configuradas y bien intervenidas pueden proporcionar un avance en la reducción de la pobreza: entorno familiar, entorno comunitario, acceso material, vivienda, acceso a la justicia, entre otros

