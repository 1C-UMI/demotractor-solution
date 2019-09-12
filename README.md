**Готовое решение "Demotractor"**

Решение предназначено для редакции Business.

Чтобы собрать расширение, нужно:

 * Установить umi.cms актуальной версии (https://github.com/Umisoft/umi.cms.2/blob/master/INSTALLATION.md);
 * Импортировать дамп базы данных `dump/dump.sql`;
 * Загрузить файлы из `src` поверх установленной umi.cms;
 * Загрузить конфигурацию упаковщика `packer/config`.php в `/sys-temp/packer/config/`;
 * Выполнить команду из корня проекта: `php packer.php /sys-temp/packer/config/config.php`;

(Настройки пакера подробнее описаны в файле `/sys-temp/packer/config/config.sample.php`)

Чтобы задеплоить решение нужно:
 * Забрать файл из `/sys-temp/packer/out/demotractor/demotractor.tar`;
 * Загрузить его в директорию `solutions` репозитория market-solutions (https://github.com/Umisoft/market-solutions);
 * Запустить сценарий "market-solutions" в teamcity (http://ci.srv32.megaserver.umisoft.ru/project.html?projectId=MarketSolutions&tab=projectOverview);
