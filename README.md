# uLogin  

Donate link: http://ulogin.ru  
Tags: ulogin, login, social, authorization  
Requires at least: 1.5  
Tested up to: 1.6.0.14  
Stable tag: 1.0.  
License: GNU General Public License, version 2  

**uLogin** — это инструмент, который позволяет пользователям получить единый доступ к различным Интернет-сервисам без необходимости повторной регистрации,
а владельцам сайтов — получить дополнительный приток пользователей из социальных сетей и популярных порталов (Google, Яндекс, Mail.ru, ВКонтакте, Facebook и др.)

## Установка

- Зайдите в административную панель сайта PrestaShop.
- В разделе "Модули" нажмите кнопку "Добавить модуль".
- В строке "Файл модуля" укажите ссылку на архив модуля ulogin.zip
- Установите модуль. Он заработает сразу после активации с настройками по умолчанию.

Более детальную информацию смотрите на сайте https://ulogin.ru/help.php

## Модуль "uLogin"

Данный модуль находится на панели администрации в разделах *"Модули"* и *"Другие"*.

Здесь задаются: 
 
**uLogin ID форма входа для панели навигации:** общее поле для всех виджетов uLogin, необязательный параметр (см. *"Настройки виджета uLogin"*);
**uLogin ID общая форма:** общее поле для всех виджетов uLogin, необязательный параметр (см. *"Настройки виджета uLogin"*);
**Текст:** заголовок, который будет выводиться перед панелью авторизации  uLogin;
**Отправлять письмо при регистрации новому пользователю:** установите флажок, если необходимо выслать письмо пользователю при регистрации с его логином и паролем;
**Группа клиентов по умолчанию:** группа, присваиваемая пользователям, зарегистрированных с помощью uLogin. По умолчанию - группа *uLogin* - создаётся после установки модуля.

## Настройки виджета uLogin

При установке расширения uLogin авторизация пользователей будет осуществляться с настройками по умолчанию.  
Для более детальной настройки виджетов uLogin Вы можете воспользоваться сервисом uLogin.  

Вы можете создать свой виджет uLogin и редактировать его самостоятельно:

для создания виджета необходимо зайти в Личный Кабинет (ЛК) на сайте http://ulogin.ru/lk.php
добавить свой сайт к списку Мои сайты и на вкладке Виджеты добавить новый виджет. После этого вы можете отредактировать свой виджет.

В графе "Возвращаемые поля профиля пользователя" вы можете включить поля **Пол** и **Дата рождения**, PrestaShop умеет использовать эти параметры для создания более подробной Статистики вашего Интернет-Магазина.

**Важно!** Для успешной работы плагина необходимо включить в обязательных полях профиля поле **Еmail** в Личном кабинете uLogin.  
Заполнять поля в графе "Тип авторизации" не нужно, т.к. uLogin настроен на автоматическое заполнение данного параметра.

Созданный в Личном Кабинете виджет имеет параметры **uLogin ID**.  
Скопируйте значение **uLogin ID** вашего виджета в соответствующее поле в настройках плагина на вашем сайте и сохраните настройки.   

Если всё было сделано правильно, виджет изменится согласно вашим настройкам.


## Особенности

Для ручного вывода панели авторизации/синхронизации в любом месте шаблона темы PrestaShop используйте smarty-переменную

		{$panel}
	
Для использования панели авторизации в хуках или контроллерах PrestaShop используйте код функции

		Ulogin::drawPanel($place, $with_label)
	
		/**
		* bool $with_label - указывает, стоит ли отображать строку типа "Войти с помощью:" 
		* рядом с виджетом (true - строка отображается). Значение по умолчанию = true
		* int $place - указывает, какую форму виджета необходимо выводить 
		* (0 - форма входа для панели навигации, 1 - общая форма). Значение по умолчанию = 0.
		*/

Для вывода списка аккаунтов пользователя используйте smarty переменную

		{$syncpanel}
	
Для использования списка аккаунтов пользователя в хуках или контроллерах PrestaShop используйте код функции

		Ulogin::getUloginUserAccountsPanel($user_id = 0)
		/**
		* int $user_id - ID пользователя. Значение по умолчанию = текущий пользователь.
		*/

## Изменения
 
####1.0.0.
* Релиз.
