# Simple Roguelike
#### Выполнила: Хорошавина Екатерина (19ПИ-2)
### Генерация комнат и содержимого
Новые комнаты не генерируются - вместо этого взаимодействие (нажатие на E) с дверью переносит игрока в начало комнаты, убирает прошлые объекты и добавляет новые (в зависимости от выбранной сложности). Обычная дверь создаёт комнату той же сложности, что и предыдущая, но без хилок; золотая дверь создаёт комнату более высокой сложности, зато добавляет две хилки на уровень. Изначально на уровне есть: две ловушки-"стража" (см. Описание объектов), стартовое кол-во движущихся и статичных ловушек (кол-во задаётся через таблицу), по одному виду каждого бонуса, две двери. На последнем уровне нет дверей и появляется конечная цель (камень).
### Принцип изменения уровня сложности
Повышение сложности делится на три этапа:

1. Если не достигнута максимальная скорость ловушек (чтобы игрок успевал прыгать от них), то будет повышаться она.
2. Если максимальная скорость ловушек достигнута, будет увеличиваться их количество до максимально возможного.
3. Если все предыдущие максимумы достигнуты, будет на единицу увеличиваться кол-во рандомных и отрицательных бонусов.
### Описание объектов
1. Ловушки-"стражи" (BP_GuirdTrap). Созданы для того, чтобы игрок не мог пройти просто вдоль стены (где реже всего спавнятся ловушки). Их скорость и траектория всегда одинаковые.
2. Двигающиеся ловушки (BP_MovingTrap). Обычные ловушки, двигающиеся из случайной точки в случайную. Скорость у всех одна, меняется вместе со сложностью.
3. Статичные ловушки (BP_StaticTrap). Стоящая на месте ловушка, появляется в случайном месте.
4. Отрицательный бонус, замедляющий игрока на некоторое время (BP_SpeedDebuff).
5. Положительный бонус, дающий игроку временный иммунитет к статичным ловушкам (BP_ImmuneBuff).
6. Положительный бонус, на время замедляющий все ловушки (BP_SpeedBuff).
7. Случайный бонус (BP_Random).
8. Бонус, дающий часть здоровья (ака хилка) (BP_Heal).

### Дополнения
Не слишком значимые, кратко укажу списком:

1. Шкала здоровья, текущий уровень и общее количество уровней реализованы как widget blueprint.
2. Сделаны интерфейсы для объектов взаимодействия (двери), для ловушек, для цели. В итоге пригодился лишь для дверей, но оставила два других.
3. Большая часть числовых значений в таблице (начиная со стартового количества ловушек и заканчивая координатами для случайного спавна).
4. Сообщения о конце игры и победе реализованы через HUD.
5. В любой момент можно перезапустить игру с самого начала (с первого уровня), нажав R.
6. Кнопки E и R добавлены в Input'ы проекта, обрабатываются в BP игрока.
### Материалы
Видео с YouTube, где взяла идею про использование интерфейса для предметов взаимодействия: https://www.youtube.com/watch?v=u4TBbtq9uwk.
И видео про healthbar: https://www.youtube.com/watch?v=PVgMkUwhtoM.


### Google disk
Если что-то где-то поломалось из-за гита, то вот ссылка на гугл диск: https://drive.google.com/drive/folders/1k0lR-A1nbAMUf7cisqYIYQNF9NypIMjV?usp=sharing
