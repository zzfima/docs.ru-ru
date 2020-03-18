---
title: Начало работы с .NET Core с помощью средств интерфейса командной строки
description: Пошаговое руководство по использованию .NET Core в Windows, Linux или macOS с помощью .NET Core CLI.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: updateeachrelease
ms.openlocfilehash: fe69521a6ac88055e3e8c8502a7e19a72667dbef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240861"
---
# <a name="get-started-with-net-core-using-the-net-core-cli"></a>Начало работы с .NET Core с помощью .NET Core CLI

В этой статье показано, как приступить к разработке приложений .NET Core для Windows, Linux и macOS с помощью .NET Core CLI.

Если вы не знакомы с .NET Core CLI, см. сведения о [пакете SDK для .NET Core](../tools/index.md).

## <a name="prerequisites"></a>Prerequisites

- [Пакет SDK для .NET Core 3.1](https://dotnet.microsoft.com/download) или более поздней версии.
- Текстовый редактор или редактор кода по вашему выбору.

## <a name="hello-console-app"></a>Первое консольное приложение

[Просмотреть или скачать пример кода](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) можно в репозитории dotnet/samples на сайте GitHub. Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Откройте командную строку и создайте папку с именем *Hello*. Перейдите в созданную папку и введите приведенную ниже команду.

```dotnetcli
dotnet new console
dotnet run
```

Вкратце рассмотрим эти команды.

01. `dotnet new console`

    [dotnet new](../tools/dotnet-new.md) создает актуальный файл проекта *Hello.csproj* с зависимостями, необходимыми для создания консольного приложения. Эта команда также позволяет создать *Program.cs* — простой файл, содержащий точку входа для приложения.

    *Hello.csproj*:

    [!code-xml[Hello.csproj](~/samples/snippets/core/tutorials/cli-create-console-app/HelloMsBuild/csharp/Hello.csproj)]

    В файле проекта указываются все данные, необходимые для восстановления зависимостей и создания программы.

    - Элемент `<OutputType>` указывает, что мы создаем исполняемый файл, то есть консольное приложение.
    - Элемент `<TargetFramework>` указывает, какая реализация.NET является целевой. В расширенном сценарии обработки можно указать несколько целевых платформ и выполнить сборку во всех средах за одну операцию. В этом руководстве рассматривается сборка только для платформы .NET Core 3.1.

    *Program.cs*:

    [!code-csharp[Program.cs](~/samples/snippets/core/tutorials/cli-create-console-app/HelloMsBuild/csharp/Program.cs)]

    Программа начинается с команды `using System`, что означает "добавить все данные пространства имен `System` в область видимости для этого файла". Пространство имен `System` включает класс `Console`.

    Затем мы определяем пространство имен с именем `Hello`. Вы можете сменить это имя на любое другое. В этом пространстве имен определяется класс с именем `Program` и методом `Main`, который принимает массив строк с именем `args`. Этот массив содержит список аргументов, передаваемых при вызове программы. В нашем примере массив не используется и программа просто выводит строку "Hello World!" "Hello World!". Позднее мы внесем в код изменения, использующие этот аргумент.

    `dotnet new` неявно вызывает [dotnet restore](../tools/dotnet-restore.md). `dotnet restore` вызывает [NuGet](https://www.nuget.org/) (диспетчер пакетов .NET) для восстановления дерева зависимостей. NuGet анализирует файл *Hello.csproj*, скачивает указанные в нем зависимости (или извлекает их из кэша на вашем компьютере) и записывает файл *obj/project.assets.json*, который требуется для компиляции и запуска примера.

02. `dotnet run`

    [dotnet run](../tools/dotnet-run.md) вызывает [dotnet build](../tools/dotnet-build.md), чтобы проверить, выполнена ли сборка целевых объектов. Затем вызывается `dotnet <assembly.dll>` для запуска целевого приложения.

    ```dotnetcli
    dotnet run
    ```

    Вы получите приведенные ниже выходные данные.

    ```console
    Hello World!
    ```

    Вместо этого вы можете выполнить `dotnet build`, чтобы скомпилировать код, не запуская консольные приложения сборки. В таком случае создается DLL-файл с готовым приложением. Файлу присваивается имя проекта. В нашем примере создается файл с именем *Hello.dll*. Это приложение можно выполнить с помощью `dotnet bin\Debug\netcoreapp3.1\Hello.dll` в ОС Windows (или `/` в системах, отличных от Windows).

    ```dotnetcli
    dotnet bin\Debug\netcoreapp3.1\Hello.dll
    ```

    Вы получите приведенные ниже выходные данные.

    ```console
    Hello World!
    ```

    При компиляции этого приложения создается исполняемый файл, формат которого зависит от операционной системы, а также `Hello.dll`. В Windows это будет `Hello.exe`, а в Linux или macOS — `hello`. Для приведенного выше примера файлу будет присвоено имя `Hello.exe` или `Hello`. Этот исполняемый файл можно запускать напрямую.

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a>Изменение программы

Давайте немного изменим программу. С числами Фибоначчи интересно работать. Поэтому давайте добавим их в программу, а также применим аргумент для приветствия пользователя приложения.

01. Замените содержимое файла *Program.cs* следующим кодом:

    [!code-csharp[Fibonacci](~/samples/snippets/core/tutorials/cli-create-console-app/fibonacci-msbuild/csharp/Program.cs)]

02. Выполните [dotnet build](../tools/dotnet-build.md) для компиляции изменений.

03. Запустите программу, передав параметр в приложение. Когда вы запускаете приложение с помощью команды `dotnet`, добавьте в конце `--`. Все, что находится справа от `--`, будет передано в приложение в виде параметра. В приведенном ниже примере в приложение передается значение `John`.

    ```dotnetcli
    dotnet run -- John
    ```

    Вы получите приведенные ниже выходные данные.

    ```console
    Hello John!
    Fibonacci Numbers 1-15:
    1: 0
    2: 1
    3: 1
    4: 2
    5: 3
    6: 5
    7: 8
    8: 13
    9: 21
    10: 34
    11: 55
    12: 89
    13: 144
    14: 233
    15: 377
    ```

Вот и все! Вы можете изменять *Program.cs* по своему усмотрению.

## <a name="working-with-multiple-files"></a>Работа с несколькими файлами

Отдельные файлы удобны для простых одиночных программ. Но при создании более сложных приложений, возможно, в проекте будет несколько файлов кода. Используем в качестве основы предыдущий пример, реализовав в нем кэширование значений Фибоначчи и рекурсию.

01. Добавьте в каталог *Hello* новый файл *FibonacciGenerator.cs* со следующим кодом:

    [!code-csharp[Fibonacci Generator](~/samples/snippets/core/tutorials/cli-create-console-app/FibonacciBetterMsBuild/csharp/FibonacciGenerator.cs)]

02. Измените метод `Main` в своем файле *Program.cs*, чтобы создать экземпляр класса new и вызвать его метод, как показано в следующем примере:

    [!code-csharp[New Program.cs](~/samples/snippets/core/tutorials/cli-create-console-app/FibonacciBetterMsBuild/csharp/Program.cs)]

03. Выполните [dotnet build](../tools/dotnet-build.md) для компиляции изменений.

04. Запустите приложение, выполнив [dotnet run](../tools/dotnet-run.md).

    ```dotnetcli
    dotnet run
    ```

    Вы получите приведенные ниже выходные данные.

    ```console
    0
    1
    1
    2
    3
    5
    8
    13
    21
    34
    55
    89
    144
    233
    377
    ```

## <a name="publish-your-app"></a>Публикация приложения

Когда все будет готово к распределению приложения, используйте команду [dotnet publish](../tools/dotnet-publish.md) для создания папки _publish_ по адресу _bin\\debug\\netcoreapp3.1\\publish\\_ (используйте `/` для систем, отличных от Windows). Содержимое папки _publish_ можно распространить на другие платформы, если на них установлена среда выполнения .NET.

```dotnetcli
dotnet publish
```

Вы получите результат, аналогичный приведенному ниже.

```console
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

Выходные данные могут отличаться от представленных выше из-за другого значения текущей папки и (или) операционной системы. Но в остальном данные будут такими же.

Запустить опубликованное приложение можно с помощью команды [dotnet](../tools/dotnet.md):

```dotnetcli
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll
```

Вы получите приведенные ниже выходные данные.

```console
Hello World!
```

Как уже упоминалось в начале статьи, создается исполняемый файл, формат которого зависит от операционной системы, а также `Hello.dll`. В Windows это будет `Hello.exe`, а в Linux или macOS — `hello`. Для приведенного выше примера файлу будет присвоено имя `Hello.exe` или `Hello`. Опубликованный исполняемый файл можно запускать напрямую.

```console
.\bin\Debug\netcoreapp3.1\publish\Hello.exe

Hello World!
```

## <a name="conclusion"></a>Заключение

Вот и все! Теперь вы можете воспользоваться изученными здесь основными концепциями, чтобы создавать собственные программы.

## <a name="see-also"></a>См. также раздел

- [Организация и тестирование проектов с помощью .NET Core CLI](testing-with-cli.md)
- [Публикация приложений .NET Core с помощью .NET Core CLI](../deploying/deploy-with-cli.md)
- [Развертывание приложений .NET Core](../deploying/index.md)
