---
title: Команда dotnet nuget add source
description: Команда dotnet nuget add source добавляет новый источник пакета в файлы конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: c1e398699c7482a69b750cde718e6f9178b5c4bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148492"
---
# <a name="dotnet-nuget-add-source"></a>dotnet nuget add source

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий

## <a name="name"></a>name

`dotnet nuget add source` — добавляет источник NuGet.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget add source [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet nuget add source` добавляет новый источник пакета в файлы конфигурации NuGet.

## <a name="arguments"></a>Аргументы

- **`PACKAGE_SOURCE_PATH`**

  Путь к источнику пакета.

## <a name="options"></a>Параметры

- **`--configfile`**

  Файл конфигурации NuGet. Если этот параметр указан, будут использоваться только параметры из этого файла. Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога. Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`-n|--name`**

  Имя источника.

- **`-p|--password`**

  Пароль, используемый при подключении к источнику, прошедшему проверку подлинности.

- **`--store-password-in-clear-text`**

  Включает сохранение учетных данных переносимого источника пакетов путем отключения шифрования паролей.

- **`-u|--username`**

  Имя пользователя, используемое при подключении к источнику, прошедшему проверку подлинности.

- **`--valid-authentication-types`**

  Разделенный запятыми список допустимых типов проверки подлинности для этого источника. Задайте значение `basic`, если сервер объявляет NTLM или Negotiate. Ваши учетные данные следует отправлять с помощью базового механизма, например, при использовании PAT с локальным Azure DevOps Server. К другим допустимым значениям относятся `negotiate`, `kerberos`, `ntlm` и `digest`, но они вряд ли будут полезны.

## <a name="examples"></a>Примеры

- Добавьте `nuget.org` в качестве источника:

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- Добавьте `c:\packages` в качестве локального источника:

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- Добавьте источник, требующий проверки подлинности:

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- Добавьте источник, требующий проверки подлинности (затем установите поставщик учетных данных):

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a>См. также

- [Разделы источников пакетов в файлах NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Команда sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
