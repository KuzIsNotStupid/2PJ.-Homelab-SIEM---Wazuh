# 2PJ.-Homelab-SIEM---Wazuh

Цель проекта
Построить домашнюю лабораторию SOC для практики мониторинга безопасности и отработки навыков работы с SIEM-системами.

Что сделано
1. Инфраструктура
- Развернута виртуальная среда в VirtualBox
- Основной сервер: Ubuntu Server 24.04 с Wazuh Manager 4.7
- Агент: Simply Linux с Wazuh Agent

2. Установка и настройка
- Установлен Wazuh Manager (серверная часть SIEM)
- Настроен Wazuh Dashboard для визуализации данных
- Развернут Wazuh Agent на удаленном хосте
- Настроен сбор security events с двух систем

3. Проверка работоспособности
- Wazuh Dashboard доступен через веб-интерфейс
- Агенты зарегистрированы в системе
- Осуществляется сбор логов безопасности
- События классифицируются по MITRE ATT&CK

Технологический стек
- Виртуализация: VirtualBox
- OС: Ubuntu Server 24.04, Simply Linux
- SIEM: Wazuh 4.7 (Elastic Stack)
- Мониторинг: Wazuh Agents, системные логи
- Сеть: TCP/IP, порт 1514 (Manager-Agent)

Приобретенные навыки
- Развертывание и настройка SIEM Wazuh в распределенной среде
- Настройка агентов на различных дистрибутивах Linux
- Диагностика сетевого взаимодействия между хостами
- Работа с Wazuh Dashboard для анализа security events
- Понимание архитектуры "Manager-Agent" в SIEM-системах

Результаты
- Wazuh Manager успешно развернут на Ubuntu
- Wazuh Dashboard доступен через веб-интерфейс
- Агент зарегистрирован на Simply Linux
- Осуществляется сбор security events
- События отображаются в Dashboard с классификацией MITRE ATT&CK

Скриншоты

1. [Wazuh Dashboard - Обзор](screenshots/dashboard.png)
2. [Список агентов](screenshots/agents.PNG)
3. [Security Event1](screenshots/securityevents.PNG)
4. [Security Event2](screenshots/securityevents2.PNG)

----

Встреченные проблемы и их решения
1. Проблема сетевой изоляции
Проблема: Виртуальные машины не видели друг друга в сети
Доказательство: Команда 'ip a' показывала разные подсети (10.0.2.15 vs другая)
Решение: Настройка Host-Only сети в VirtualBox вместо NAT

2. Ошибка установки на Simply Linux
Проблема: wazuh.gpg: команда не найдена
Причина: Simply Linux использует RPM-пакеты (yum), а не DEB (apt)
Решение:
- Создал каталог для репозиториев
sudo mkdir -p /etc/yum.repos.d/
- Настроил правильный репозиторий
sudo tee /etc/yum.repos.d/wazuh.repo << 'EOF'
[wazuh]
name=Wazuh repository
baseurl=https://packages.wazuh.com/4.x/yum/
gpgcheck=1
gpgkey=https://packages.wazuh.com/key/GPG-KEY-WAZUH
enabled=1
EOF

3. Ошибки ввода команд Wazuh
Проблема: Неправильное использование утилиты manage_agents
Ошибки:
-1 вместо -l для списка агентов
-a без указания IP и имени
Использование угловых скобок в командах
Решение: Изучил справку команд (-h) и правильный синтаксис

4. Ошибки Wazuh API
Проблема: Wazuh API error: ERR_BAD_RESPONSE
Причина: Нехватка ресурсов в виртуальной среде
Решение: Увеличил RAM VM до 7GB, оптимизировал настройки JVM
