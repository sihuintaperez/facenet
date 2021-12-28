# Facenet 
alumno:Luis Sihuinta Perez


## Workflow
### Clone the repository
Clonar el repositorio
```
git clone https://github.com/davidsandberg/facenet.git
```

### Instalar los requerimientos
El repositorio provee un archivo .txt para instalar los requerimientos con el siguiente comando

```
cd facenet
pip install –r requirements.txt
```
### Descargar un modelo pre-entrenado
El modelo usado se puede descargar [aqui](https://drive.google.com/file/d/1EXPBSXwTaqrSC0OhUdXNmKSh9qJUQ55-/view) 
Este .rar es extraido en la siguiente carpeta `~/facenet-master/mymodel/`, dentro deberia crearse una carpeta con el nombre `20180402-114759`

### Entrenar un clasificador 
Para entrenar un clasificador debemos de tener un modelo y un dataset, el comando es el siguiente.

```
cd facenet
python src/classifier.py TRAIN [PATH DEL DATASET] [PATH DEL MODELO] [PATH DONDE GUARDAREMOS EL CLASIFICADOR] --batch_size 1000
```
Un ejemplo seria :

```
cd facenet
python src/classifier.py TRAIN ~/.spyder-py3/grafica/proyecto/facenet-master/dataset/lfw_mini_masked/ ~/.spyder-py3/grafica/proyecto/facenet-master/mymodel/20180402-114759/20180402-114759.pb ~/.spyder-py3/grafica/proyecto/facenet-master/mymodel/lfw_classifier_masked.pkl --batch_size 1000 
```

### Testeo del clasificador 

Para verificar la precision de nuestro clasificador necesitamos de :
-Un datatest
-Modelo preentrenado
-Clasificador (el que hemos usado)

El comando es el siguiente :

```
cd facenet
python src/classifier.py CLASSIFY [PATH DEL DATATEST] [PATH DEL MODELO] [PATH DONDE GUARDARMOS NUESTRO CLASIFICADOR] --batch_size 1000
```

un ejemplo:
```
cd facenet
python src/classifier.py CLASSIFY ~/.spyder-py3/grafica/proyecto/facenet-master/dataset/lfw_mini_test/ ~/.spyder-py3/grafica/proyecto/facenet-master/mymodel/20180402-114759/20180402-114759.pb ~/.spyder-py3/grafica/proyecto/facenet-master/mymodel/lfw_classifier_masked.pkl --batch_size 1000
```
