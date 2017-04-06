# Everyware

Documentación de los archivos JSON
[Terapia Online]


Estructura básica de los ficheros:

    {
      "title": "", Título del cuestionario.
      "subtitle":"", Subtítulo del cuestionario.*
      "description": "", Descripción del cuestionario (solo a nivel interno, no se verá reflejado).*
      "questions": [ Listado de preguntas del cuestionario.
        {
          "title": "", Título de la pregunta.
          "subtitle": "", Subtítulo de la pregunta.*
          "description": "", Descripción de la pregunta (solo a nivel interno, no se verá reflejado).*
          "legend": "", Leyenda de las posibles respuestas (en caso de ser necesaria).*
          "category": "" Categoría (o tipo) de la pregunta.
        },
      ]
    }

*De no existir se asignará el valor null.



Categorías:

Categoría 1:
Pregunta tipo linear_scale, se dispone de varios números de respuesta exclusiva. Por ejemplo: 

    Valore su satisfacción con el programa

           0       1       2       3       4       5       6       7       8       9        10
                                 
          Nada                                                                              Muy
       satisfecho                                                                        satisfecho

Este tipo de pregunta tiene los siguientes atributos:
  •	legend[]: Leyenda, array con los valores de cada posible respuesta. Por ejemplo:
    "legend": [
      "Nada satisfecho",
      "Poco satisfecho",
      "Bastante satisfecho",
      "Muy satisfecho"
    ]

  •	start y end: Indicando el primer y el último número de la escala. Por ejemplo:
    "start": "0",
    "end": "10"

  •	labels[]: Array con las etiquetas de la escala. Por ejemplo:
    "labels": [
      "Nada satisfecho",
      "Muy satisfecho"
    ]


 
Categoría 2:
Pregunta tipo dropdown, se dispone de una lista desplegable con respuesta exclusiva. Por ejemplo: 

      Indique el tiempo que suele dedicar a jugar a las distintas categorías de videojuegos expuestas.
      1.	No suelo jugar nunca.
      2.	Suelo jugar en alguna ocasión.
      3.	Suelo jugar una vez por semana.
      4.	Suelo jugar varias veces por semana.
      5.	Suelo jugar a diario.

      Videojuegos de acción: _______ 
      Videojuegos de conducción: _______
      Videojuegos de ROL: _______

Este tipo de pregunta tiene los siguientes atributos:
  •	legend[]: Leyenda, array con los valores de cada posible respuesta. Por ejemplo:
    "legend": [
      "No suelo jugar nunca",
      "Suelo jugar en alguna ocasión",
      "Suelo jugar una vez por semana",
      "Suelo jugar varias veces por semana",
      "Suelo jugar a diario"
    ]

  •	values: Array con los distintos valores que se mostrarán en el desplegable. Por ejemplo:
    "legend": [
      "1",
      "2",
      "3",
      "4",
      "5"
    ]
  •	answer: Array con cada una de las preguntas que hay que responder. Por ejemplo:
    "legend": [
      "Videojuegos de acción",
      "Videojuegos de conducción",
      "Videojuegos de ROL"
    ]

 
Categoría 3:
Pregunta tipo question_list, con distintas subpreguntas y distintas respuestas. Por ejemplo:
Lea cada frase y marque la respuesta que más se ajuste a su vida diaria.
  1.	Suelo ver la televisión.
    a.	Todos los días.
    b.	A veces.
    c.	Nunca.
  2.	Salgo a caminar.
    a.	A diario.
    b.	No muy a menudo.
    c.	Nunca.


Este tipo de pregunta tiene los siguientes atributos:
  •	subquestions[]: Array con las distintas subpreguntas, que a su vez se componen de un título y un array con sus distintas respuestas. Por ejemplo:
    "subquestions": [
      {
        "title": "Suelo ver la televisión",
        "answer": [
          "Todos los días",
          "A veces",
          "Nunca"
        ]
      },
      {
         "title": "Salgo a caminar",
         "answer": [
           "A diario",
           "No muy a menudo",
           "Nunca"
         ]
       },
     ]




 
Categoría 4:
Pregunta tipo question_list con distintas subpreguntas y las mismas respuestas. Por ejemplo:
Marque las plataformas de videojuegos que posee.
  1.	PlayStation 3.
    a.	Si.
    b.	No.
  2.	Nintendo 3DS.
    a.	Si.
    b.	No.


Este tipo de pregunta tiene los siguientes atributos:
  •	subquestions[]: Array con las distintas subpreguntas. Por ejemplo
    "subquestions": [
      "PlayStation 3",
      "Nintendo 3DS"
     ]

  •	answer[]: Array con las posibles respuestas. Por ejemplo:
    "answer": [
      "Si",
      "No"
     ]



 
Categoría 5: 
Pregunta tipo question_list con respuesta numérica exclusiva. Por ejemplo:

Indique si le gustan los Sistemas Operativos que se muestran.
  1.	No me gusta nada.
  2.	Me gusta poco.
  3.	Me gusta bastante.
  4.	Me encanta.

  1.	iOS          1  2  3  4 
  2.	Windows 10   1  2  3  4
  3.	Android      1  2  3  4  

Este tipo de pregunta tiene los siguientes atributos:
  •	legend[]: Leyenda, array con los valores de cada posible respuesta. Por ejemplo:
    "legend": [
      "No me gusta nada",
      "Me gusta poco",
      "Me gusta bastante",
      "Me encanta"
    ]

  •	start y end: Indicando el primer y el último número de la escala. Por ejemplo:
      "start": "1",
      "end": "4"

  •	subquestions[]: Array con las distintas subpreguntas. Por ejemplo
      "subquestions": [
        "iOS",
        "Windows 10",
        "Android"
      ]



 
Categoría 6:
Pregunta única con respuesta exclusiva.

      ¿Cuál es su marca de smartphone favorita?.
      •	iPhone.
      •	Sony.
      •	Samsung.

Este tipo de pregunta tiene los siguientes atributos:
  •	answer: Array con las posibles respuestas. Por ejemplo:
    "legend": [
      "iPhone",
      "Sony",
      "Samsung"
    ]


Categoría 7:
Preguntas con respuesta única de tipo short_text. Por ejemplo:

    1.	¿Cuánto tiempo emplea usted viendo la televisión?
    Indique el tiempo en minutos: _______

    2.	¿A qué hora suele irse a dormir?
    Indique su hora de acostarse: _______


Este tipo de pregunta tiene los siguientes atributos:
  •	subquestions[]: Array con las distintas subpreguntas, que a su vez se componen de un título y un subtítulo. Por ejemplo:
    "subquestions": [
      {
        "title": "¿Cuánto tiempo emplea usted viendo la televisión?",
        "answer": "Indique el tiempo en minutos"
      },
      {
         "title": "¿A qué hora suele irse a dormir?",
         "answer": "Indique su hora de acostarse"
       },
     ]



Categoría 8:
Al igual que la categoría 4, pregunta tipo question_list con distintas subpreguntas y las mismas respuestas EXCEPTO la última, que deja la subpregunta libre al usuario. Solo existe una:

  Durante el último mes cuántas veces ha tenido usted problemas para dormir a causa de:
  1.	No poder conciliar el sueño en la primera media hora.
    a.	Ninguna vez en el último mes.
    b.	Menos de una vez en el último mes.
    c.	Una o dos veces a la semana.
    d.	Tres o más veces a la semana.
  2.	Despertarse durante la noche o de madrugada.
    a.	Ninguna vez en el último mes.
    b.	Menos de una vez en el último mes.
    c.	Una o dos veces a la semana.
    d.	Tres o más veces a la semana.
  3.	Otras razones (por favor descríbalas a continuación):
  ___________________________________________
    a.	Ninguna vez en el último mes.
    b.	Menos de una vez en el último mes.
    c.	Una o dos veces a la semana.
    d.	Tres o más veces a la semana.


Este tipo de pregunta tiene los siguientes atributos:
  •	subquestions[]: Array con las distintas subpreguntas:
    "subquestions": [
      "No poder conciliar el sueño en la primera media hora",
      "Despertarse durante la noche o de madrugada",
      "Otras razones (por favor descríbalas a continuación):"
     ]

  •	answer[]: Array con las posibles respuestas:
    "answer": [
      "Ninguna vez en el último mes",
      "Menos de una vez en el último mes",
      "Una o dos veces a la semana",
      "Tres o más veces a la semana"
     ]


 
Categoría 9
Al igual que la categoría 5, pregunta tipo question_list con respuesta numérica exclusiva, pero con secciones. Por ejemplo:

    Indique si le gustan los Sistemas Operativos que se muestran.
        1.	No me gusta nada.
        2.	Me gusta poco.
        3.	Me gusta bastante.
        4.	Me encanta.

    Sistemas Operativos de escritorio:
    1.	OS X         1  2  3  4 
    2.	Windows 10   1  2  3  4
    3.	Ubuntu       1  2  3  4  

    Sistemas Operativos móviles:
    4.	iOS          1  2  3  4
    5.	Android      1  2  3  4


Este tipo de pregunta tiene los siguientes atributos:
  •	legend[]: Leyenda, array con los valores de cada posible respuesta. Por ejemplo:
    "legend": [
      "No me gusta nada",
      "Me gusta poco",
      "Me gusta bastante",
      "Me encanta"
    ]

  •	start y end: Indicando el primer y el último número de la escala. Por ejemplo:
    "start": "1",
    "end": "4"

  •	subquestions[]: Array con las distintas secciones, que a su vez se componen del nombre de la sección y la lista de preguntas de cada sección. Por ejemplo
    "subquestions": [
      {
        "title": "Sistemas Operativos de escritorio",
        "questions": [
          "OS X",
          "Windows 10",
          "Ubuntu"
        ]
      },
      {
         "title": "Sistemas Operativos móviles",
         "questions": [
           "iOS",
           "Android"
         ]
       },
     ]

