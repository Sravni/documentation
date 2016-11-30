## Оглавление
1. [Подготовка](#start)
2. [Виджеты](#widgets)
3. [Микровиджеты](#microwidgets)
4. [Если что-то не работает](#solutions)

## <a name='start'>Подготовка</a>
### Добавление скрипта
  Для начала необходимо подключить на страницу основной скрипт:
  
  ```
  <script src="//f.sravni.ru/f/apps/build/widgets/sravni-widgets.js"></script>
  ```
  Скрипт является общим для всех типов виджетов и **должен быть подключен в одном экземпляре**.
  
## <a name='widgets'>Виджеты</a>
### Подключение
  1. Проверяем подключен ли скрипт - пункт [подготовка](#start)
  2. Добавляем компонент на страницу в нужное место. 
    Виджет отобразится сдвоенным с переключателем типа **каско | осаго** *(при копировании кода не забудьте указать свой partner.id в атрибуте partner)*:

    ```
    <sravni-widget partner="partner.id"></sravni-widget>
    ```
    Допустимые параметры:      
<table cellspacing=0 border=1>
					<tr>
						<th style="min-width:50px; text-align: center"50px>Параметры / Сервис</th>
						<th style="min-width:50px; text-align: center"50px>Автострахование</th>
						<th style="min-width:50px; text-align: center"50px>Подбор кредита</th>
						<th style="min-width:50px; text-align: center"50px>Страхование путешествий (Beta)</th>
						<th style="min-width:50px; text-align: center"50px>Описание</th>
					</tr>
					<tr>
						<td style="min-width:50px" colspan=5><b>Основные</b></td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>type</td>
						<td style="min-width:50px; text-align: center"50px>kasko/osago</td>
						<td style="min-width:50px; text-align: center"50px>credits</td>
						<td style="min-width:50px; text-align: center"50px>mantravel</td>
						<td style="min-width:50px">Тип виджета (если атрибут не указан, устанавливается двойной виджет автострахования, где первым отображается каско)</td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>logo </td>
						<td style="min-width:50px; text-align: center"50px>true/false</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px">Отображение логотипа Сравни.ру. По умолчнию отображается. Для отключения нужно установить logo="false".</td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>first</td>
						<td style="min-width:50px; text-align: center"50px>kasko/osago</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px">Первая вкладка для двойного виджета</td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>partner</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px">Атрибут для указания идентификатора партнёра. Необходим для фиксации переходов и расчётов с виджета в личном кабинете на partner.sravni.ru. При отсутствии атрибута будет взято имя хоста. Например, если партнёр выкладывает виджет на внутренней странице сайта bestsite.com/news/16/07/freshnews и не указывает атрибут partner, то проверяться на предмет наличия партнёрства будет bestsite.com</td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>width</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px">ширина виджета. Может задаваться в %, либо абсолютным значением. Опциональный, по умолчанию 100% ширины контейнера</td>
					</tr>
					<tr>
						<td style="min-width:50px" colspan=5 ><b>Дополнительные</b></td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>responsive</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px">Адаптивный виджет. Опциональный. Задает нужный тег viewport, если на странице он отсутствует</td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>theme</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px">Тема оформления виджета. Принимает текстовое значение и применяет стили соответствующей темы</td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>hide-partners</td>
						<td style="min-width:50px; text-align: center"50px>true/false</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px">Правило отображения блока со страховыми партнёрами</td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>order-by</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px">имя_страховой_компании</td>
						<td style="min-width:50px">Атрибут для отображения предложений указаной страховой в начале списка с лейблом "рекомендовано". Страховая указывается при помощи алиаса (например, reso)</td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>query</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px">строка_запроса</td>
						<td style="min-width:50px">Строка запроса к виджету передаёт параметры по умолчанию для загрузки виджета с заранее установленными параметрами</td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>self-payment</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px; text-align: center"50px>-</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px">Параметр для реализации оплаты полиса на стороне партнёра (требует доработок на сайте партнёра). Предоставляет api для получения данных об оплате. Для осуществления данной возможности свяжитесь с нами.</td>
					</tr>
					<tr>
						<td style="min-width:50px" colspan=5><b>Трекинг</b></td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>data-pixel-lead</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px">Если вы используете сбор статистики при помощи пикселей или переменную sub_id в UTM метках на своём сайте, вы можете указать их в значениях этих атрибутов. Пиксели будут регистрироваться каждый раз, когда происходит соответствующее событие в виджете. Атрибут sub_id регистрируется при выполнении заказа</td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>data-pixel-engage</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px"></td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>sub</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px"></td>
					</tr>
					<tr>
						<td style="min-width:50px" colspan=5><b>Сервисные</b></td>
					</tr>
					<tr>
						<td style="min-width:50px; text-align: center"50px>server</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px; text-align: center"50px>+</td>
						<td style="min-width:50px">Сервисная переменная для указания сервера подгружаемого файла виджета. При встраивании партнёром не указывается</td>
					</tr>
				</table>     
  3. Задать ширину виджета можно, обернув его в контейнер необходимой ширины, либо указать параметр при подключении:
   
    ```
    <sravni-widget width="600" partner="partner.id"></sravni-widget>
    ```
  4. Чтобы виджет работал корректно на мобильных устройствах, на странице должен быть установлен корректный viewport:
  
    ```
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    ```

## <a name='microwidgets'>Микровиджеты</a>
### Подключение
  1. Проверяем подключен ли скрипт - пункт [подготовка](#start)
  2. Добавляем один или несколько компонентов на страницу в нужное место *(при копировании кода не забудьте указать свой partner.id в атрибуте partner)*:
  
    ```
    <sravni-micro-widget type="osago" logo="true" partner="partner.id"></sravni-micro-widget>
    ```
    Допустимые параметры
    * logo - параметр для отображения логотипа Сравни.ру. Может принимать значения true или false. Если не указан, по умолчанию принимает значение true - т.е. отображается</li>
    * size - ширина виджета. Параметр необязательный, и в случае, если не установлен, виджет примет ширину контейнера в момент вставки
    * type - тип или типы сервиса. <b>Атрибут обязателен. Если указано некорректное значение, микровиджет отображаться не будет</b>. Допустимые значения атрибута:
        - type="osago" : для ОСАГО
        - type="kasko" : для КАСКО
        - type="mantravel" : для Страхования путешествий
        - type="osago,kasko" : комбинированный с переключателем для ОСАГО и КАСКО. Первым будет отображён микровиджет ОСАГО
        - type="kasko,osago" : комбинированный с переключателем для КАСКО и ОСАГО. Первым будет отображён микровиджет КАСКО
    * partner (адрес/имя партнёра) - необязательный параметр - по умолчанию хост со страницы
    * server - адрес api сервера. Опциональный (используется для тестирования). По умолчанию https://www.sravni.ru
    * hide-partners - атрибут, отключающий блок партнёров под микровиджетом. Атрибут достаточно добавить в код микровиджета не присваивая никакого значения
    * sticker - атрибут, добавляющий стикер "реклама" к микровиджету
  3. Ограничения
    - Не следует вписывать виджет в контейнер с шириной меньше 550 пикселей без установки атрибута size
  
## <a name='solutions'>Если что-то не работает</a>
### Не вставляется тег виджета (например, в CMS Wordpress). 
  Оберните виджет Сравни в тег script следующим образом (на примере микровиджета):

  ```
  <script>document.write('<sravni-micro-widget type="mantravel"></sravni-micro-widget>')</script>
  ```
### Ваш сайт использует старые библиотеки (например mootools версии 1.2) и *микровиджет* не отображается. 
  1. Создайте статичную html страницу на вашем сайте и сделайте её доступной по прямой ссылке (sitename.ru/microwidget.html). Статичная страница должна включать только базовую разметку (html, head, body, meta).
  2. Разместите виджет на статичной странице согласно документации.
  3. Откройте редактор страницы, на которой должен отображаться виджет и добавьте следующий код:
  
    ```
    <iframe frameborder="0" src="ссылка/на/статичную/страницу.html" style="width:700px; height: 400px;"></iframe>
    ```
  4. Укажите ссылку на вашу статичную страницу из п. 1 в атрибут src и установите необходимую ширину и высоту
  
  *Примечание* 
    Если внутри тега iframe не умещаются календари (для туристического микровиджета), убрать их можно установкой атрибута field-datepicker="false", например:

    ```
    <sravni-micro-widget type="mantravel" logo="true" partner="partner.id" field-datepicker="false"></sravni-micro-widget>
    ```
