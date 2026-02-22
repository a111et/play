
# Прохождение Play Integrity на Android 16 QPR2

### Устройство: Poco F6 | Прошивка: Project Infinity X v3.7

Этот метод базируется на связке **KernelSU Next** и **TEE Simulation**, что позволяет добиться прохождения всех трех проверок (MEETS_DEVICE_INTEGRITY, MEETS_BASIC_INTEGRITY и MEETS_STRONG_INTEGRITY).

---

## 1. Подготовка системы (Критически важно)

Перед установкой модулей необходимо привести систему в "первозданный" вид, иначе встроенные в прошивку фиксы будут конфликтовать с модулями.

* **Отключите все встроенные спуфинги:** Зайдите в настройки прошивки (обычно Infinity Space или Developer Options) и выключите:
* Spoof Google Play
* Spoof Google Photos (Безлимитные фото).
* Spoof Netflix/Snapchat/Games.
* И т.д если есть


* **Ядро:** Используйте ядро с **KernelSU Next** (если нету такого ядра то патч `init_boot.img`). Версия "Next" лучше скрывает само наличие рута на новых версиях Android.

---

## 2. Необходимый софт и модули

Установите следующие компоненты в указанном порядке:

| Компонент | Назначение | Настройка |
| --- | --- | --- |
| **Zygisk Next** | Альтернатива обычному Zygisk |  |
| **Перезагрузка** |||
| **Play Integrity Fix** | Подмена фингерпринта | Обычно работает "из коробки". |
| **TEE Simulator** | Эмуляция доверенной среды | Пункт 3 |
| **Tricky Store Enhanced** | Хранилище ключей | Пункт 3 |
| **Перезагрузка** |||

---
## 3. Тонкая настройка

**Настройка Zygisk Next:**

1. Зайти в настройки Zygisk Next
2. Включить: Use anonymous memory и Use Zygisk Next linker.
`Это надо для скрытия Zygisk ибо есть случаи как определяется Zygisk и это нарушает сертификацию`

**Настройка TEE:**

1. 3 точки сверхуй справа 
2. Выбрать все приложени
3. Отменить выбор ненужного
4. Keybox -> Действительный
5. Установить verified boot hash
6. Установить Security patch нажать **Авто**

---

## 4. Сброс данных (Очистка хвостов)

Чтобы Google Play "поверил" в новую реальность, нужно стереть старые логи детектов. Остановите и **очистите кэш и данные** (Clear Data) у следующих приложений:

1. Google Play Store (Маркет).
2. Google Wallet (Кошелек).
3. Google Play Services (Сервисы Google — здесь важно очистить всё через "Управление местом").

---

## 5. Проверка результата

* **Play Integrity API Checker:** Должны гореть 3 зеленые галочки (включая Strong Integrity).
* **Google Play:** Настройки -> Сведения -> Сертификация устройства -> **"Устройство сертифицировано"**.

---

## Полезные ссылки

* [KernelSU Next](https://github.com/rifsxd/KernelSU-Next) — Ядро с улучшенным скрытием.
* [Zygisk Next](https://github.com/Dr-TSNG/ZygiskNext) — Модуль для работы скриптов.
* [Play Integrity Fix (Telegram)](https://t.me/keybox_xml) — Актуальные фингерпринты.
* [Tricky Addon Enhanced](https://github.com/Enginex0/tricky-addon-enhanced) — Форк для работы с Keybox.
* [TEE Simulator](https://github.com/Enginex0/TEESimulator) — Эмуляция TEE.

---

> **Совет:** Если после обновления прошивки оплата отвалилась, первым делом проверяйте актуальность вашего `pif.json` в модуле Play Integrity Fix.

