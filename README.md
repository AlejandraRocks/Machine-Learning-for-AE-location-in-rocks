# Machine Learning para localizar-Emisión Acústica EA en Rocas

Mi tema de tesis de doctorado esta enmarcado en el estudio de las ondas de Emision Acustica como precursores de grandes sismos, asi que decidi enfocar este trabajo práctico en buscar alguna aplicación a mi tema. Las emisiones acústicas (EA) son las ondas de tensión producidas por la repentina redistribución de la tensión interna de los materiales causada por los cambios en la estructura interna. Los cambios en la estructura interna pueden ser la iniciación de grietas dentro de la roca, apertura de grietas, fracturamiento, etc. La mayoría de las fuentes de EA están relacionadas con los daños; por lo tanto, la correcta localizacion de estas emisiones se utilizan habitualmente para predecir el fallo de los materiales. 

![image](https://github.com/AlejandraRocks/-Machine-Learning-para-localizar-Emisi-n-Ac-stica-EA-en-Rocas-/assets/69768600/0dc72c51-48af-4cb4-85ee-7edcc8a97122)

Para localizar las fuentes de EA usualmente se utilizan metodos similares al campo de la sismologia, y los más utilizados son los métodos de inversión del tiempo de recorrido de la onda (Geiger 1912; Aki y Lee 1976). Estos métodos se centran en torno al objetivo de resolver la relación no lineal entre el tiempo de viaje y la localización del hipocentro, lo que requiere modelos de velocidad constante predefinidos del medio (Richards et al.
2006). Para el caso caso que me interesa (localizacion de EA en rocas) la tarea se convierte en algo muy dificil cuando la roca tiene anisotropia. Esto requiere inversion tomografica de la muestra para establecer un modelo de velocidad y luego una inversion iterativa para localizar, lo cual es computacionalmente caro. En este trabajo práctico usaré algunos métodos de  Machine Learning para localizar la coordenada x,y usando solo los tiempos de arribo de la onda P, para eludir por completo la complejidad de establecer un modelo de velocidades y el proceso interativo de inversión. 

# **1. Adquisición de los datos**

Como por la pandemia aun no he podido realizar ensayos experimentales con mis muestras. Decidi buscar datos de ensayos de rotura de emision acústica en articulos donde liberaran los datos. Este es el caso de [blue_text](https://en.x-mol.com/paper/article/1225011219574341632). El montaje experimental consiste en un marco de carga, un sistema de registro EA  y el montaje de la muestra de roca (Fig. 1a). El montaje experimental se hizo con una muestra de roca tipo granito con dimensiones 218 mm x 218 mm x 200 mm  con un plano vertical de 45 grados en el centro (simulando una falla de laboratorio). Luego se aplica tension a la roca para obtener un deslizamiento por cizallamiento lateral derecho
en la falla de laboratorio a una tensión normal de falla de 10 MPa. Once sensores  piezoeléctricos  tipo Glaser fijados a la
a la muestra de roca en los lados norte (N) y oeste (W). Estos sensores se conectan directamente al digitalizador, que está conectado al computador  que registra las señales de EA.

<img width="707" alt="montaje" src="https://github.com/AlejandraRocks/-Machine-Learning-para-localizar-Emisi-n-Ac-stica-EA-en-Rocas-/assets/69768600/495ff562-0cd7-4c70-991c-2deb2b49f521">

Se ralizaron 56 pruebas simulando una fuente de  EA mediante la 
ruptura de la mina de lápiz de 0,7 mm de diámetro en lugares conocidos
en la superficie de la falla (Hsu et al. 1978), antes de realizarse el ensayo de ruptura sobre la falla. Estos eventos se reparten por
toda la  superficie de la falla para asegurar una buena cobertura espacial. El tiempo de las ondas P se estimo con el criterio Akaike Information Criterion (AIC). A continuacion se muestra un ejemplo de como se recibio la señal en cada sensor y el picking de la onda P.

<img width="633" alt="descargar" src="https://github.com/AlejandraRocks/-Machine-Learning-para-localizar-Emisi-n-Ac-stica-EA-en-Rocas-/assets/69768600/3cdfecb7-b22a-498c-98b7-9854ba3baa46">








