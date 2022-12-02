#  PROYECTO RECONOCIMIENTO FACIAL


## Sobre el repositorio
En este proyecto se realiza el reconocimiento de atributos entrenando una red con la base de datos de CelebA que se puede encontrar en kaggle.
Esta base de datos contiene mas de 200,000 imagenes de rostros de famosos, ademas de un archivo de texto que etiqueta los atributos que hay en cada imagen, como cabello negro, nariz grade, lentes, etc. 

![image](https://user-images.githubusercontent.com/114697211/203874181-02dbed9a-f6e2-4f52-8c78-5963ff974248.png)

## Vista general
Para la primera parte del proyecto necesitamos entrenar un modelo con imagenes de rostro, de forma que el modelo aprenda a identificar caracteristicas en imagenes, una vez logrado esto podemos reutilizar este modelo para crear otro con un objetivo distinto, el de reconocer mi rostro. 

Esta tecnica de entrenar un modelo con una base grande y luego reutilizarlo para crear otro modelo con otro fin se conoce como Transfer learning y es una tecnica muy poderosa para crear nuevos modelos y muy eficientes a partir de otros. 

## Descripcion del proyecto 
Como primer paso importamos las paqueterias necesarias y cargamos los datos de CelebA, los cuales consisten en una lista de atributos y una carpeta con imagenes, e iniciamos con el procesamiento de datos. Al ser dos tipos de datos completamente distintos, cada uno se procesa de cierta forma, para la lista de atributos lo mas conveniente es convertirla a un csv y se realizo una limpieza de datos. 


<img width="952" alt="Screen Shot 2022-11-24 at 5 47 47 PM" src="https://user-images.githubusercontent.com/114697211/203875512-d60f8b07-f622-4b0f-992b-dc09e65303a5.png">


Para las imagenes procedemos a definir su ruta y realizamos el procesamiento de imagenes que corresponde a la normalizacion de la intensidad de los pixeles y redimensionar. 

<img width="1107" alt="image" src="https://user-images.githubusercontent.com/114697211/203880636-d6e93225-d8b3-4830-8c6c-ef5b854cfc59.png">

despues se hace la union de estos dos datos, entrada por entrada, cada imagen con su correspondiente lista de atributos. 


Una vez realizado el procesamiento de datos, podemos definir el modelo. Este consistira de redes convolucionales para el procesamiento de imagenes y asociacion de atributos, despues aplanaremos la red para usar redes densas y que nuestros datos de salida sean listas con los correspondientes atributos de la imagen que se tome como entrada. 
Usamos el optimizador rmsprop, la funcion loss binary_crossentropy y una metrica binaria. 

<img width="1006" alt="image" src="https://user-images.githubusercontent.com/114697211/203875988-07292e6a-96fc-47b8-8199-893a65f89daa.png">

Por ultimo entrenamos la red.











