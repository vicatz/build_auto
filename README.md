Утилиты для автоматизации загрузки и настройки toolchain и подготовки ядра к прошивке.
Скачиваем в удобное место:
git clone https://github.com/rezvorck/build_auto.git
Выполняем из директории исходников ядра:
export ARCH=архитектура && export CROSS_COMPILE=$(путь_до_скрипта/toolchain.sh параметр)
В параметре можно указать путь куда будем загружать toolchain (например ../) или оставить пустым.
После того как ядро скомпилировано выполняем:
путь_до_скрипта/auto.sh boot recovery
В параметре передаются образы каторые надо собрать. После окончания работы скрипта в корне исходника
будет архив для прошивки через рекавери.
В boot/архитектура/ ложем расспакованный boot, то же самое для recovery.
Если необходимо собрат только образ, ложем скомпилированный kernel в соответствующую папку
переименовав в boot.img-kernel и выполняем repack.sh boot. Образ recovery собирается по аналогии.
