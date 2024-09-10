# Инструкция к VLESS
VLESS - это подобие шифрованного прокси, маскирующегося под HTTPS трафик.

Вы можете использовать любой удобный клиент, главное **чтобы он поддерживал ядро sing-box**.

В этой инструкции я порекомендую два клиента, которые подойдут пользователям в зависимости от их предпочтений **Hiddify** и **NekoRay**

| [Hiddify](#hiddify) | [NekoRay](#nekoray) |
| ------- | ------- |
| ✅ Простой, красивый и понятный интерфейс | ✴️ Более сложный и функциональный интерфейс |
| ✅ Настрока одной кнопкой | ✴️ Настройка в нескольких подменю которые еще надо найти |
| ✴️ Отсутствуют фильтры и шаблоны. В VLESS отправляется или весь ваш трафик, или весь трафик за исключением Российского (если выбран регион Россия) | ✅ Есть возможность задать любые фильтры по доменам, IP адресам, geoip и правила маршрутизации |
| Платформы: IOS (только IPA), Android (включая TV), Windows, macOS, Linux | Платформы: Windows, Linux, Android (NekoBox) |

При желании, вы можете использовать разные клиенты для разных устройств или для разных ситуаций.

## Hiddify

<img src="https://github.com/user-attachments/assets/d57391ee-d479-4122-9a67-08ecc9db60a3" width=60% />

### Скачивание

<a href="https://play.google.com/store/apps/details?id=app.hiddify.com"><img height=50px src="https://github.com/hiddify/hiddify-next/blob/main/docs/google-play-badge.png?raw=true"></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

<div align=left>
<table>
    <thead align=left>
        <tr>
            <th>Операционная система</th>
            <th>Скачать</th>
        </tr>
    </thead>
    <tbody align=left>
        <tr>
        <td>iOS</td>
            <td>
                <a href="https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify-iOS.ipa"><img src="https://img.shields.io/badge/IPA-Universal-c0c0c0.svg?logo=ios"></a>
            </td>
        </tr>
        <tr>
        <td>Android</td>
            <td>
                <a href="https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify-Android-universal.apk"><img src="https://img.shields.io/badge/APK-Universal-044d29.svg?logo=android"></a><br>
                <a href="https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify-Android-arm64.apk"><img src="https://img.shields.io/badge/APK-ARMv8-168039.svg?logo=android"></a><br>
                <a href="https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify-Android-arm7.apk"><img src="https://img.shields.io/badge/APK-ARMv7-45bf55.svg?logo=android"></a><br>
                <a href="https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify-Android-x86_64.apk"><img src="https://img.shields.io/badge/APK-x64-96ed89.svg?logo=android"></a>
            </td>
        </tr>
        <tr>
            <td>Windows</td>
            <td>
                <a href="https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify-Windows-Setup-x64.exe"><img src="https://img.shields.io/badge/Setup-x64-2d7d9a.svg?logo=windows"></a><br>
                <a href="https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify-Windows-Portable-x64.zip"><img src="https://img.shields.io/badge/Portable-x64-67b7d1.svg?logo=windows"></a>
            </td>
        </tr>
        <tr>
            <td>MacOS</td>
             <td>
                <a href="https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify-MacOS.dmg"><img src="https://img.shields.io/badge/DMG-Universal-ea005e.svg?logo=apple"></a><br>
                <a href="https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify-MacOS-Installer.pkg"><img src="https://img.shields.io/badge/PKG-Universal-bc544b.svg?logo=apple" /></a>
            </td>
        </tr>
        <tr>
            <td>Linux</td>
            <td>
                <a href="https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify-Linux-x64.AppImage"><img src="https://img.shields.io/badge/AppImage-x64-f84e29.svg?logo=linux"> </a><br>
                <a href="https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify-Debian-x64.deb"><img src="https://img.shields.io/badge/DebPackage-x64-FF9966.svg?logo=debian"> </a><br>
                <a href="https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify-rpm-x64.rpm"><img src="https://img.shields.io/badge/RpmPackage-x64-F1B42F.svg?logo=redhat"> </a>
            </td>
        </tr>
    </tbody>
</table>

### Подключение

Для подключения скопируйте ссылку профиля, затем нажмите **добавить профиль -> Добавить из буфера обмена**.

По умолчанию для российских пользователей обращения к российским IP и .ru доменам будет происходить напрямую. Если вы хотите направить их через VLESS, перейдите в раздел **Параметры конфигурации** и поменяйте **Регион** на **Другой**

Хорошо работают 2 режима работы:
1. **Системный прокси** (только на десктопных клиентах) - Hiddify прописывается как системный прокси и приложения сами отправляют трафик через него. Тем не менее, некоторые приложения могут отправлять трафик в обход системного прокси.
2. **VPN** - Hiddify создает TUN/TAP интерфейс и работает как VPN, перенаправляя весь трафик через себя. Для этого режима необходим запуск Hiddify с правами администратора. Можно навсегда прописать запрос таких прав в свойствах .exe файла.

## NekoRay

<img src="https://github.com/user-attachments/assets/39eef7ce-762c-46c1-aba0-a584665e9f47" width=60% />

### Скачивание
- NekoRay - клиент под Windows/Linux. [**Ссылка для скачивания NekoRay**](https://github.com/MatsuriDayo/nekoray/releases/latest)
- NekoBox - клиент под Android. [**Ссылка для скачивания NekoBox**](https://github.com/MatsuriDayo/NekoBoxForAndroid/releases/latest) (в GooglePlay фейк)
### Подключение
1. Для подключения скопируйте ссылку профиля, затем нажмите **Программа -> Добавить профиль из буфера обмена**.
2. Чтобы запустить или остановить профиль **ПКМ по профилю -> Запустить/Остановить**
3. Чтобы трафик шел через NekoRay должна быть установлена галочка **Режим TUN** или **Режим системного прокси** (разницу см. в разделе Hiddify). При отключении профиля галочку необходимо убирать, иначе интернет-соединения не будет. Стоит галочка - трафик идет в NekoRay, не стоит идет обычным путем.
4. Настройки фильтрации при необходимости можно добавить в **Настройки -> Настройки маршрутов -> Вкладка Базовые маршруты**. В нижнем правом углу задается назначение трафика, который не соответствует фильтрам. Примеры фильтров можно посмотреть загрузив китайский **Пресет**. Можно создать несколько наборов машрутов (первая вкладка) и переключаться между ними в **Программа -> Активное правило роутинга**.
