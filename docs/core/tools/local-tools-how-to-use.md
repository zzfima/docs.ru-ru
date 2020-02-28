---
title: Учебник. Установка и использование локальных средств .NET Core
description: Узнайте, как устанавливать и использовать средство .NET в качестве локального.
ms.date: 02/12/2020
ms.openlocfilehash: 6de620772cec1e9d1b1f57380b72c0163d68337c
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543818"
---
# <a name="tutorial-install-and-use-a-net-core-local-tool-using-the-net-core-cli"></a>Учебник. Установка и использование локального средства .NET Core с помощью интерфейса командной строки .NET Core

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий

В этом учебнике вы узнаете, как установить и использовать локальное средство. Вы используете инструмент, созданный в [первом учебнике этой серии](global-tools-how-to-create.md).

## <a name="prerequisites"></a>Предварительные требования

* Выполните действия из [первого руководства этой серии](global-tools-how-to-create.md).
* Установите среду выполнения .NET Core 2.1.

  В данном учебнике вы установите и используете средство, нацеленное на .NET Core 2.1, поэтому вам необходимо установить эту среду выполнения на ваш компьютер. Чтобы установить среду выполнения 2.1, перейдите на [страницу загрузки .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1) и найдите ссылку на установку среды выполнения в колонке **Run apps — Runtime** (Запуск приложений — среда выполнения).

## <a name="create-a-manifest-file"></a>Создание файла манифеста

Чтобы установить средство только для локального доступа (для текущего каталога и подкаталогов), его необходимо добавить в файл манифеста. 

Из папки *botsay-\<name>* перейдите на один уровень вверх к папке *репозиторий*:

```console
cd ..
```

Создайте файл манифеста, выполнив команду [dotnet new](dotnet-new.md):

```dotnetcli
dotnet new tool-manifest
```

Выходные данные свидетельствуют об успешном создании файла.

```console
The template "Dotnet local tool manifest file" was created successfully.
```

Файл *.config/dotnet-tools.json* пока не имеет в себе никаких средств:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

Средства, перечисленные в файле манифеста, доступны для текущего каталога и подкаталогов. Текущим является каталог, содержащий каталог *.config* с файлом манифеста.

При использовании команды CLI, которая относится к локальному средству, пакет SDK ищет файл манифеста в текущем каталоге и родительских каталогах. Если он находит файл манифеста, но файл не включает указанное средство, поиск продолжается по родительским каталогам. Поиск заканчивается после нахождения указанного средства или файла манифеста с `isRoot` установленным на `true`.

## <a name="install-botsay-as-a-local-tool"></a>Установка botsay в качестве локального средства

Установите средство из пакета, который вы создали в первом учебнике:

```dotnetcli
dotnet tool install --add-source ./botsay-<name>/nupkg botsay-<name>
```

Эта команда добавляет средство в файл манифеста, созданный на предыдущем шаге. Вывод команды показывает, в каком файле манифеста находится только что установленное средство:

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'botsay-<name>' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

Файл *.config/dotnet-tools.json* теперь содержит одно средство:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay-<name>": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    }
  }
}
```

## <a name="use-the-tool"></a>Работа со средством

Запустите средство, выполнив команду `dotnet tool run` из папки *репозиторий*:

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a>Восстановление локального инструмента, установленного другими пользователями

Обычно вы устанавливаете локальное средство в корневой каталог репозитория. После записи файла манифеста в репозиторий после изменения, другие разработчики получают последний файл манифеста. Чтобы установить все средства, перечисленные в файле манифеста, они могут запустить всего лишь одну команду `dotnet tool restore`.

1. Откройте файл *.config/dotnet-tools.json* и замените его содержимое на следующий JSON:

   ```json
   {
     "version": 1,
     "isRoot": true,
     "tools": {
       "botsay-<name>": {
         "version": "1.0.0",
         "commands": [
           "botsay"
         ]
       },
       "dotnetsay": {
         "version": "2.1.3",
         "commands": [
           "dotnetsay"
         ]
       }
     }
   }
   ```

1. Замените `<name>` именем, использованным для создания проекта.

1. Сохраните изменения.

   Внесение этого изменения аналогично получению последней версии из репозитория после установления пакета `dotnetsay` для каталога проекта другим пользователем. 

1. Выполните команду `dotnet tool restore`.

   ```dotnetcli
   dotnet tool restore
   ```

   После выполнения команды должен появиться результат, подобный приведенному ниже.

   ```console
   Tool 'botsay-<name>' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. Убедитесь, что средства доступны:

   ```dotnetcli
   dotnet tool list
   ```

   Выходные данные представляют собой список пакетов и команд, как показано в следующем примере:

   ```console
   Package Id      Version      Commands       Manifest
   -------------------------------------------------------------------------------------------
   botsay-<name>   1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
   dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
   ```

1. Протестируйте средства:

   ```dotnetcli
   dotnet tool run dotnetsay hello from dotnetsay
   dotnet tool run botsay hello from botsay
   ```

## <a name="update-a-local-tool"></a>Обновление локального средства

Установленная версия локального средства `dotnetsay` — 2.1.3.  Последней является версия 2.1.4. Используйте команду [dotnet tool update](dotnet-tool-update.md), чтобы обновить средство до последней версии.

```dotnetcli
dotnet tool update dotnetsay
```

В выходных данных указывается новый номер версии:

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.4'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

Команда update находит первый файл манифеста, содержащий идентификатор пакета, и обновляет его. Если такой идентификатор пакета отсутствует в любом файле манифеста, находящегося в области поиска, пакет SDK добавляет новую запись в ближайший файл манифеста. Область поиска поднимается вверх по родительским каталогам, пока не будет найден файл манифеста с `isRoot = true`.

## <a name="remove-local-tools"></a>Удаление локального средства

Удалите установленные средства, выполнив команду [dotnet tool uninstall](dotnet-tool-uninstall.md):

```dotnetcli
dotnet tool uninstall botsay-<name>
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a>Устранение неполадок

Если при выполнении учебника появляется сообщение об ошибке, см. статью [Устранение неполадок при использовании средства .NET Core](troubleshoot-usage-issues.md).

## <a name="see-also"></a>См. также

Дополнительные сведения см. в статье [Обзор глобальных средств .NET Core](global-tools.md).
