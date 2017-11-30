---
title: "Начало работы с C# и Visual Studio Code - руководство по C#"
description: "Узнайте, как создать и отладить в Visual Studio Code свое первое приложение .NET Core на языке C#."
keywords: "C#, приступая к работе, получение, установка, Visual Studio Code, кроссплатформенный"
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
ms.openlocfilehash: 3a9de689946507e4b6d89f684461d65049b3375a
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="get-started-with-c-and-visual-studio-code"></a>Начало работы с C# и Visual Studio Code

.NET Core предcтавляет собой быструю модульную платформу для создания приложений, работающих на ОС Windows, Linux и macOS. Visual Studio Code с расширением C# позволяет эффективно работать с кодом, а также обеспечивает полную поддержку IntelliSense (интеллектуальное завершение кода) и отладки для языка C#.

## <a name="prerequisites"></a>Предварительные требования

1. Установите [Visual Studio Code](https://code.visualstudio.com/).
2. Установите [пакета SDK для .NET Core](https://www.microsoft.com/net/download/core).
3. Установите [расширение C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) из Marketplace для Visual Studio Code.

## <a name="hello-world"></a>Hello World

Давайте начнем с создания простой программы Hello World для .NET Core.

1. Откройте проект.

    * Откройте Visual Studio Code.
    * Щелкните значок обозревателя в расположенном слева меню, затем щелкните**Открыть папку**.
    * Выберите **файл** > **открыть папку** в главном меню, чтобы открыть папку нужно проект C# в и нажмите кнопку **Выбор папки**. В нашем примере мы создаем папку для проекта с именем *HelloWorld*.

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. Инициализируйте проект C#.
    * Откройте интеграции терминалов из кода Visual Studio, выбрав **представление** > **интеграции терминалов** в главном меню.
    * В окне терминала введите `dotnet new console`.
    * Эта команда создает `Program.cs` файл в папке с программой простой «Hello World», уже написанный вместе с файлом проекта C# с именем `HelloWorld.csproj`.

      ![Команда dotnet new](media/with-visual-studio-code/dotnetnew.png)

3. Выполните разрешение для средств сборки:

    * Для **.NET Core 1.x**, тип `dotnet restore`. Команда `dotnet restore` предоставляет доступ к пакетам .NET Core, которые необходимы для сборки этого проекта.

      ![Команда dotnet restore](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. Запустите программу Hello World.

    * Введите `dotnet run`. 

      ![Команда dotnet run](media/with-visual-studio-code/dotnetrun.png)

Вы можете просмотреть небольшие видеоматериалы с информацией о процессе настройки для [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), или [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).

## <a name="debug"></a>Отладка

1. Откройте файл *Program.cs*, щелкнув его. При первом открытии файла C# в Visual Studio Code [OmniSharp](http://www.omnisharp.net/) загружает в редакторе.

    ![Откройте файл Program.cs](media/with-visual-studio-code/opencs.png)

2. Visual Studio Code запросит отсутствующих ресурсов для построения и отладки приложения. Выберите ответ **Да**. 

    ![Предупреждение о недостающих ресурсах](media/with-visual-studio-code/missing-assets.png)

3. Чтобы открыть окно отладки, щелкните значок "Отладка" в меню слева.

    ![Откройте вкладку "Отладка"](media/with-visual-studio-code/opendebug.png)

4. Найдите зеленую стрелку в верхней части панели. Убедитесь, что в раскрывающемся списке рядом с ней выбран вариант `.NET Core Launch (console)`.

    ![Выбор .NET Core](media/with-visual-studio-code/selectcore.png)

5. Добавьте точку останова в проект, щелкнув **поле редактора**, это место в левой части номера строк в редакторе, рядом с строке 9.

    ![Установка точки останова](media/with-visual-studio-code/setbreakpoint.png)

6. Чтобы начать отладку, выберите <kbd>F5</kbd> или зеленой стрелкой. Отладчик останавливает выполнение программы, когда достигнет точки останова, которую вы только что установили.
    * Во время отладки можно просматривать локальных переменных в левой верхней панели или с помощью консоли отладки.

    ![Запуск и отладка](media/with-visual-studio-code/rundebug.png)

7. Выберите зеленую стрелку в верхней части, чтобы продолжить отладку, или выберите красный квадрат в верхней части, чтобы остановить процесс.

> [!TIP] 
> Дополнительные сведения и советы по отладке .NET Core в Visual Studio Code с помощью OmniSharp см. в разделе [Инструкции по настройке отладчика .NET Core](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).

## <a name="see-also"></a>См. также
[Настройка Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)   
[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Отладка в Visual Studio Code)
