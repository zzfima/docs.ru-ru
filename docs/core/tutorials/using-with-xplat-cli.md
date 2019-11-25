---
title: Начало работы с .NET Core с помощью средств интерфейса командной строки
description: Пошаговое руководство, описывающее начало работы с .NET Core в Windows, Linux или macOS с помощью интерфейса командной строки (CLI) .NET Core.
author: thraka
ms.author: adegeo
ms.date: 08/07/2019
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: cf8c3ae070f4c77789dc55ba4d7888c7b15c8653
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736990"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a>Начало работы с .NET Core в Windows, Linux и Mac OS с помощью командной строки

В этом разделе показано, как приступить к разработке кроссплатформенных приложений с помощью средств интерфейса командной строки (CLI) .NET Core.

Если вы не знакомы с набором средств CLI .NET Core, прочитайте [обзор пакета SDK для .NET Core](../tools/index.md).

## <a name="prerequisites"></a>Предварительные требования

- [Пакет SDK для .NET Core 2.1](https://dotnet.microsoft.com/download) или более поздней версии.
- Текстовый редактор или редактор кода по вашему выбору.

## <a name="hello-console-app"></a>Первое консольное приложение

[Просмотреть или скачать пример кода](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) можно в репозитории dotnet/samples на сайте GitHub. Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Откройте командную строку и создайте папку с именем *Hello*. Перейдите в созданную папку и введите следующую команду:

```dotnetcli
dotnet new console
dotnet run
```

Вкратце рассмотрим эти команды.

1. `dotnet new console`

   С помощью [`dotnet new`](../tools/dotnet-new.md) создается актуальный файл проекта *Hello.csproj* с зависимостями, необходимыми для создания консольного приложения. Эта команда также позволяет создать *Program.cs* — простой файл, содержащий точку входа для приложения.

   *Hello.csproj*:

   [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]

   В файле проекта указываются все данные, необходимые для восстановления зависимостей и создания программы.

   - Тег `OutputType` указывает, что мы создаем исполняемый файл — другими словами, консольное приложение.
   - Тег `TargetFramework` указывает, какая реализация.NET является целевой. В расширенном сценарии обработки можно указать несколько целевых платформ и выполнить сборку во всех средах за одну операцию. В этом руководстве рассматривается сборка только для платформы .NET Core 2.1.

   *Program.cs*:

   [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]

   Программа начинается с команды `using System`, что означает "добавить все данные пространства имен `System` в область видимости для этого файла". Пространство имен `System` включает класс `Console`.

   Затем мы определяем пространство имен с именем `Hello`. Вы можете сменить это имя на любое другое. Класс `Program` определяется в этом пространстве имен с использованием метода `Main`, который принимает массив строк в качестве аргумента. Этот массив содержит список аргументов, передаваемых при вызове скомпилированной программы. В такой форме программа не использует этот массив. Единственное ее действие — вывод надписи "Hello World!" в консоль. Позднее мы внесем в код изменения, использующие этот аргумент.

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

   `dotnet new` неявно вызывает [`dotnet restore`](../tools/dotnet-restore.md). `dotnet restore` вызывает [NuGet](https://www.nuget.org/) (диспетчер пакетов .NET) для восстановления дерева зависимостей. NuGet анализирует файл *Hello.csproj*, скачивает указанные в нем зависимости (или извлекает их из кэша на вашем компьютере) и записывает файл *obj/project.assets.json*, который требуется для компиляции и запуска примера.

   > [!IMPORTANT]
   > Если вы используете пакет SDK для .NET Core 1.x, необходимо самому вызвать `dotnet restore` после вызова `dotnet new`.

2. `dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) вызывает [`dotnet build`](../tools/dotnet-build.md) для проверки того, выполнена ли сборка целевых объектов, а затем вызывает `dotnet <assembly.dll>` для запуска целевого приложения.

    ```console
    $ dotnet run
    Hello World!
    ```

    Кроме того, вы можете выполнить [`dotnet build`](../tools/dotnet-build.md), чтобы скомпилировать код, не запуская консольные приложения сборки. В результате мы получаем скомпилированное приложение в виде файла DLL, которое можно выполнить с помощью `dotnet bin\Debug\netcoreapp2.1\Hello.dll` в Windows или `/` в других операционных системах. Вы также можете указать аргументы для приложения, как описано ниже.

    ```console
    $ dotnet bin\Debug\netcoreapp2.1\Hello.dll
    Hello World!
    ```

    В расширенном сценарии можно собрать приложение в качестве автономного набора файлов для определенной платформы, которые можно развернуть и запустить на компьютере без .NET Core. Чтобы получить подробные сведения, см. статью [.NET Core Application Deployment](../deploying/index.md) (Развертывание приложений .NET Core).

### <a name="augmenting-the-program"></a>Расширение программы

Давайте немного изменим программу. С числами Фибоначчи интересно работать, поэтому давайте добавим следующее в дополнение к использованию аргумента для приветствия пользователя приложения.

1. Замените содержимое файла *Program.cs* следующим кодом:

   [!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]

2. Выполните [`dotnet build`](../tools/dotnet-build.md) для компиляции изменений.

3. Запустите программу, передав параметр в приложение:

   ```console
   $ dotnet run -- John
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

Вот и все!  Вы можете расширять файл *Program.cs* по своему усмотрению.

## <a name="working-with-multiple-files"></a>Работа с несколькими файлами

Отдельные файлы хороши для простых одиночных программ, но при создании более сложных приложений, возможно, в проекте будет несколько исходных файлов.
Используем в качестве основы предыдущий пример, реализовав в нем кэширование значений Фибоначчи и рекурсию.

1. Добавьте в каталог *Hello* новый файл *FibonacciGenerator.cs* со следующим кодом:

   [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

2. Измените метод `Main` в своем файле *Program.cs*, чтобы создать экземпляр класса new и вызвать его метод, как показано в следующем примере:

   [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. Выполните [`dotnet build`](../tools/dotnet-build.md) для компиляции изменений.

4. Запустите приложение, выполнив [`dotnet run`](../tools/dotnet-run.md). Ниже приведены выходные данные программы:

   ```console
   $ dotnet run
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

Когда вы будете готовы к распространению приложения, используйте команду [`dotnet publish`](../tools/dotnet-publish.md) для создания папки _publish_ в _bin\\debug\\netcoreapp 2.1.\\publish\\_ (используйте `/` для систем, отличных от Windows). Содержимое папки _publish_ можно распространить на другие платформы, если на них установлена среда выполнения .NET.

Запустить опубликованное приложение можно с помощью команды [dotnet](../tools/dotnet.md):

```console
$ dotnet bin\Debug\netcoreapp2.1\publish\Hello.dll
Hello World!
```

## <a name="conclusion"></a>Заключение

Вот и все! Теперь вы можете воспользоваться изученными здесь основными концепциями, чтобы создавать собственные программы.

## <a name="see-also"></a>См. также

- [Организация и тестирование проектов с помощью инструментов командной строки .NET Core](testing-with-cli.md)
- [Публикация приложений .NET Core с помощью интерфейса командной строки](../deploying/deploy-with-cli.md)
- [Подробнее о развертывании приложений](../deploying/index.md)
