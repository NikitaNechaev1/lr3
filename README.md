# lr3
Лабораторная работа #3<br />
Методы аугментации данных<br />
Цель лабораторной работы : Добавить методы аугментации данных в цикл обучения
сверточной нейронной сети для восстановления информации в цветовых каналах
изображения
Задачи:<br />
1. Используя окружение для обучения нейронной сети из лабораторной работы #2
выполнить:<br />
""" при выполнении пунктов 1а-1d картинки были подготовлены используя 1 tf-record на 1 картинку. По этой причине на 5 - 12 эпохе заполнялась оперативная память. На количестве картинок ~60 000 эта проблема была решена путём увеличения числа картинок в одном tf-record файле (уменьшения числа shards). Train - 5000 кадров фильмов "Шестиструнный самурай" и "Ничего хорошего в отеле Эль Рояль", validation - 500 фотографий из личного архива """<br />
    a. Обучить нейронную сеть с использованием метода аугментации ‘случайная
часть изображения’<br />
Аугментация:<br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_crop_1.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_crop_2.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_crop_3.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_crop_4.png)<br />
Результат обучения:<br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_crop_results_graph.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_crop_results_image.png)
    b. Обучить нейронную сеть с использованием метода аугментации ‘случайное
горизонтальное отражение’<br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_flip_1.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_flip_2.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_flip_3.png)<br />
Результат обучения:<br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_flip_results_graph.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_flip_results_image.png)
    c. Обучить нейронную сеть с использованием метода аугментации ‘поворот на
случайный угол’
    d. Обучить нейронную сеть используя методы аугментации a-с
2. Подготовить набор данных из минимум 50000 изображений и повторить на нем
пункт 1.d
