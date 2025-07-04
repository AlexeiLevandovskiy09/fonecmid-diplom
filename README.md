# Дипломный проект профессии «1C-программист: с нуля до middle» (Левандовский А. Н.)
 ## Выполнены все задания
## Кастомизация конфигурации «Управление IT-фирмой для компании «Ваш компьютерный мастер»

### Цель дипломного проекта

Разработать и подготовить к эксплуатации новый функциональный блок в конфигурации «Управление IT-фирмой».

- реализовать новые подсистемы «Работа с заявками клиентов» и «Расчёт управленческой зарплаты» в соответствии с требованиями заказчика,
- подготовить отчёты по новой функциональности,
- оформить инструкцию по начальной настройке,
- подготовить автотест для проверки корректности работы подсистемы «Работа с заявками клиентов»,
- загрузить результат работы в новый репозиторий на GitHub.

## Решение
## Описание дополненного функционала

## 1. Добавлена подсистема Обслуживание клиентов

### Документ Обслуживание клиентов

Процесс работы с заявками построен следующим образом:

Клиент звонит менеджеру и оставляет заявку на работу специалиста с указанием проблемы, для решения которой нужен специалист.
Менеджер ищет свободное время и планирует заявку на это время.
При планировании телеграм-бот оповещает специалистов о появлении новой заявки.
Специалист в назначенное время в офисе клиента или удалённо проводит необходимые работы.
Специалист получает подписанный лист учёта рабочего времени или скан/фото листа учёта от клиента. В листе учёта перечисляются виды работ, выполненные специалистом, и фиксируется количество часов к оплате. В дальнейшем документ будет являться подтверждением проведения работ.
Специалист вносит в информационную систему информацию о выполненных работах, количество фактически потраченных часов на каждый вид работы, количество часов к оплате клиенту за каждый вид работы и прикрепляет к документу скан/фото листа учёта рабочего времени.

#### Документы Обслуживание клиентов вводят специалисты и менджеры. 
Для работы с данным документом созданы предопределенные профили пользователей BKM_Специалист и BKM_Менеджер по обслуживанию

####  Документ Реализации товаров и услуг

В документе Реализации товаров и услуг добавлена возможность выбора договора с видом абонентская плата, с возможностью автозаполнения этого документа суммой ежемесячной абонентской платы и суммой за выполненные в течения месяца работы по данным документов Обслуживание клиентов. Из документа  печатается акт об оказанных услугах.

####  Документ Реализации товаров и услуг использует бухгалтер.
 Для работы с данным документом создан предопределенный профиль пользователей BKM_Бухгалтер.

###  Обработка Массовое создание документов Реализация товаров и услуг
В начале месяца бухгалтер фирмы формирует акты по всем абонентским договорам. Данный процесс автоматизирован.

#### Массовое создание документов Реализации использует бухгалтер.
Для работы с данной обработкой создана роль BKM_Массовое создание документов Реализации. Эта роль подключена к предопределенному профилю пользователей BKM_Бухгалтер.

## 2. Добавлена подсистема Расчёт управленческой зарплаты

На предприятии работают сотрудники двух категорий: специалисты и административный персонал. Специалистам начисляется минимальный оклад и процент за выполненные работы клиентам. Административный персонал получает оклад. Любому сотруднику на усмотрение руководства может быть начислена разовая фиксированная премия. С каждого сотрудника удерживается НДФЛ -13%.

### Для расчета зарплаты используется два документа:

- Начисление заработной платы.
- Начисление фиксированной премии.

### Планирование отпусков.

Механизм позволяет составлять график отпусков. Данные нужно вносить в начале года.

### Контроль заполнения графиков отпусков

Для визуального контроля пересечения отпусков сотрудника предусмотрена процедура контроля. При нажатии на кнопку Анализ графика открывается форма с диаграммой Ганта с информацией о каждом сотруднике.

#### Подсистема Расчёт управленческой зарплаты
Для работы с подсистемой Расчёт управленческой зарплаты создан предопределенный профиль пользователей BKM_Кадровик-расчетчик.

## 3. Отчеты
### Выработка специалистов.
Отчёт показывать, сколько часов за выбранный период отработал выбранный специалист и какая сумма ему за этот период начислена в виде процента от выплат клиента.

### Анализ выставленных актов
Отчёт включать информацию о клиентах, договорах и суммах, которые должны быть выставлены клиентам на основе данных из документов Обслуживание. 

### Расчеты с сотрудниками
В отчете представлена информация о том, какие суммы начислены и выплачены каждому сотруднику за указанный период. Также в отчете отражена задолженность на начало и на конец этого периода.

### Расход запланированных отпусков
Пользователи строит отчёт за конкретный год. Отчет показывать сколько дней отпуска у сотрудника в выбранный период по плану и сколько дней он фактически был в отпуске.

## 3. Добавлена подсистема ДобавленныеОбъекты
В данную подсистему включены все объекты добавленные в процессе доработки. Данную подсистему может видеть только администратор. 

# Инструкция по начальной настройке и эксплуатации новых инструментов

## При первом запуске необходимо настроить дополнительный функционал Программного обеспечения.

### Все настройки осуществляются в режиме 1С предприятия:

1. Создать пользователя с правами доступа Администратор (Профиль пользователя Администратор)
2. Создать пользователей с правами доступа BKM_Бухгалтер, BKM_Кадровик-расчетчик, BKM_Специалист, BKM_Менеджер по обслуживанию выбрав соответствующий профиль пользователя

### Подсистема Обслуживание клиентов.
1. В режиме администратора настроить [телеграмм-бот](https://github.com/AlexeiLevandovskiy09/fonecmid-diplom/blob/main/tasks/telegram.md)
2. Настроить регламентное задание по отправке сообщений телеграмм-боту.
3. Из полученных данных настройки Телеграмм-бота заполнить Константы BKM_ТокенУправленияТБотом и BKM_ИдентификаторГруппыОповещения
4. Создать номенклатуру (или выбрать существующую) с видом номенклатуры Услуги, которая будет отображаться в актах об оказании услуг клиенту.
Рекомендуется Абонентская плата и Работы специалиста.
Заполнить созданными (выбранными) наименованиями соответствующие константы: BKM_НоменклатураАбонентскаяПлата и BKM_НоменклатураРаботыСпециалиста.


### Перед первым использованием подсистемы Обслуживание клиентов, Кадровику-расчетчику необходимо 
1. Подсистема Обслуживание клиентов использует справочник BKM_Сотрудники.
На данном этапе справочник пуст.
2. Кадровик-расчетчик в обязательном порядке должен заполнить справочник Сотрудники фамилиями сотрудника фирмы, а так же заполнить регистр сведения УсловияОплатыСотрудников поле ПроцентОтВыполненныхРабот. Поля регистра сведения о гафике работы сотрудника и окладу можно заполнить позже.

### Перед первым использованием подсистемы Расчет зарплаты.
1. Заполнить справочник графики работ. Например Пятидневка, шестидневка. Для графика отпуск имеется предопределенная запись - Отпуск календарные дни. 
2. С помощью обработки Заполнение графиков работ, заполните соответствующий график. В поле обработку Выходные дни указываются дни недели цифрами (Подряд без пробелов), которые являются выходными. Например для графика пятидневка поле заполняется значением "67".
3. Кадровик-расчетчик в обязательном порядке должен дополнить регистр сведения УсловияОплатыСотрудников поля о гафике работы сотрудника и окладу. 
4. Кадровик-расчетчик должен  в разделе сервис назначить график работ для отпуска (Должны учитываться все дни)
   
# Тестирование

## Сценарии
- Планирование двух обслуживаний на специалистов от имени Менеджера
- Закрытие обслуживаний от имени Специалиста
- Массовое создание актов от имени Бухгалтера
- Формирование отчета Анализ выставленных актов 

## Автотесты реализованы с помощью Vanessa Automation.
#### Настройки и условия для успешного прохождения тестов.
1. Все автотесты запускаются на приложенной [базе данных](https://github.com/AlexeiLevandovskiy09/fonecmid-diplom/blob/main/1Cv8.dt).
В этой базе настроены предопределенные данные и заполнены справочники тестовыми данными.
2. Перед запуском автотеста клиент-тест должен быть закрыт.
3. Автотестирование должно проходить в строгой последовательности, так как некоторые тесты оприаются на данные созданными другими тестами.
   - 1. Первым идет запуск автотестирования из файла Создание_документов_Обслуживание_клиента.feature.
   - 2. Затем - Закрытие_документа_Обслуживание_клиента.feature
   - 3. Затем - Групповое_создание_актов.feature
   - 4. Для последнего тестирования необходимо сохранить на компьютер файлы из репоитория Ноябрь.mxl и Октябрь.mxl.
        На закладке "Сервис-Основные" Менеджера тестирования в строке "Каталог проекта" прописать путь к папке, где сохранены эти файлы.
4. После запуска вышеуказанного пакета можно повторно запускать тесты в произвольном порядке. 
