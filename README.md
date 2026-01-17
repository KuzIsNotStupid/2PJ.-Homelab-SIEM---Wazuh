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

1. Wazuh Dashboard - Обзор
https://github.com/KuzIsNotStupid/2PJ.-Homelab-SIEM---Wazuh/blob/main/screenshots/dashboard.png

2. Список агентов
https://github.com/KuzIsNotStupid/2PJ.-Homelab-SIEM---Wazuh/blob/main/screenshots/agents.png

3. Security Events
a. https://github.com/KuzIsNotStupid/2PJ.-Homelab-SIEM---Wazuh/blob/main/screenshots/security events.png
b. https://github.com/KuzIsNotStupid/2PJ.-Homelab-SIEM---Wazuh/blob/main/screenshots/security events2.png
