### Готовое решение "Demotractor"

#### Общая информация:

 * Решение предназначено для редакции Business, но может работать на всех редакциях, вплоть до Lite;
 * Объект решения production версии: (http://udod.umihost.ru/admin/updatesrv/edit/479361/);
 * Объект решения dev версии: (http://udod.umihost.ru/admin/updatesrv/edit/496780/);
 * Настройки конфигурации упаковщика подробнее описаны в файле (https://github.com/Umisoft/umi.cms.2/blob/dev/sys-temp/packer/config/config.sample.php);
 * Инструкция по установке системы: (https://github.com/Umisoft/umi.cms.2/blob/dev/INSTALLATION.md);
 * При любой сборке надо ставить ставить заглушку на сайт через config.ini [stub], чтобы во время сборки боты не добавили вам в бд спама;

#### Чтобы собрать production версию, нужно:
 * Установить umi.cms production версии без шаблона, пропуская шаг импорта дампа базы данных (https://github.com/Umisoft/umi.cms.2/blob/master/INSTALLATION.md);
 * Импортировать дамп базы данных `dump/dump.sql`;
 * Изменить адрес домена в таблице `cms3_domains` на свой и переактивировать систему (убедитесь что в вашем ключе нет лишних модулей и расширений);
 * Обновить umi.cms принудительно до production версии;
 * Снять дамп базы данных и сохранить его по пути `dump/dump.sql`;
 * Загрузить файлы из `src/files/` поверх установленной umi.cms;
 * Удостовериться, что сайт открывается и работает базовый функционал (например: открываются все типы страниц);
 * Загрузить конфигурацию упаковщика `packer/config.php` в `/sys-temp/packer/config/`;
 * Выполнить команду из корня проекта: `php classes/system/commands/Packer.php sys-temp/packer/config/config.php`;

#### Чтобы задеплоить production версию, нужно:
 * Забрать файл из `/sys-temp/packer/out/demotractor/demotractor.tar`;
 * Загрузить его в директорию `solutions` репозитория market-solutions (https://github.com/Umisoft/market-solutions);
 * Запустить сценарий "market-solutions" в teamcity (http://ci.srv32.megaserver.umisoft.ru/project.html?projectId=MarketSolutions&tab=projectOverview);
 
#### Чтобы установить production версию, нужно:
 * Через gui: на этапе выбора шаблона при установке cms надо выбрать "Адаптивный сайт компании" (http://help.docs.umi-cms.ru/vvedenie/ustanovka_i_nastrojka/vybor_sajta/);
 * Через cli: указать в install.ini [DEMOSITE] name = "demotractor" (https://github.com/Umisoft/umi.cms.2/blob/master/install.ini.original);
 * Через репозиторий: импортировать дамп базы данных `dump/dump.sql` и загрузить файлы из `src/files/` поверх установленной production версии umi.cms без шаблона ;

#### Чтобы собрать dev версию, нужно:
 * Установить umi.cms dev версии без шаблона, пропуская шаг импорта дампа базы данных (https://github.com/Umisoft/umi.cms.2/blob/master/INSTALLATION.md);
 * Импортировать дамп базы данных `dump/dump-dev.sql`;
 * Изменить адрес домена в таблице `cms3_domains` на свой и переактивировать систему (убедитесь что в вашем ключе нет лишних модулей и расширений);
 * Обновить umi.cms принудительно до dev версии;
 * Снять дамп базы данных и сохранить его по пути `dump/dump-dev.sql`;
 * Загрузить файлы из `src/files/` поверх установленной umi.cms;
 * Удостовериться, что сайт открывается и работает базовый функционал (например: открываются все типы страниц);
 * Загрузить конфигурацию упаковщика `packer/config-dev.php` в `/sys-temp/packer/config/`;
 * Выполнить команду из корня проекта: `php classes/system/commands/Packer.php sys-temp/packer/config/config-dev.php`;
 
#### Чтобы задеплоить dev версию, нужно:
 * Забрать файл из `/sys-temp/packer/out/demotractor-dev/demotractor-dev.tar`;
 * Загрузить его в директорию `solutions` репозитория market-solutions (https://github.com/Umisoft/market-solutions);
 * Запустить сценарий "market-solutions" в teamcity (http://ci.srv32.megaserver.umisoft.ru/project.html?projectId=MarketSolutions&tab=projectOverview);
  
#### Чтобы установить dev версию, нужно:
 * Через gui: нужно указать в объекте лицензии в поле "Оплаченные решения" = "demotractor-dev" и выбрать его в разделе "Мои покупки" на этапе выбора шаблона (http://help.docs.umi-cms.ru/vvedenie/ustanovka_i_nastrojka/vybor_sajta/);
 * Через cli: нужно указать в объекте лицензии "Оплаченные решения" = "demotractor-dev" и указать в install.ini [DEMOSITE] name = "demotractor-dev" (https://github.com/Umisoft/umi.cms.2/blob/dev/install.ini.original);
 * Через репозиторий: импортировать дамп базы данных `dump/dump-dev.sql` и загрузить файлы из `src/files/` поверх установленной dev версии umi.cms без шаблона;
