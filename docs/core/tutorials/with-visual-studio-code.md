---
title: "Начало работы с C# и Visual Studio Code — руководство по языку C#"
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
ms.workload: dotnetcore
ms.openlocfilehash: 95052da1688ec1026f11ff679dda6aad50a340fa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
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
    * Выберите **Файл** > **Открыть папку** в главном меню, чтобы открыть папку, в которой вы хотите разместить проект C#, и щелкните **Выбрать папку**. В нашем примере мы создаем для проекта папку с именем *HelloWorld*.

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. Инициализируйте проект C#.
    * Откройте в Visual Studio Code интегрированный терминал, выбрав **Просмотр** > **Интегрированный терминал** в главном меню.
    * В окне терминала введите `dotnet new console`.
    * Эта команда создает в выбранной папке файл `Program.cs` с уже готовой простой программой Hello World, а также файл проекта C# с именем `HelloWorld.csproj`.

      ![Команда dotnet new](media/with-visual-studio-code/dotnetnew.png)

3. Выполните разрешение для средств сборки:

    * Для **.NET Core 1.x** введите `dotnet restore`. Команда `dotnet restore` предоставляет доступ к пакетам .NET Core, которые необходимы для сборки этого проекта.

      ![Команда dotnet restore](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. Запустите программу Hello World.

    * Введите `dotnet run`. 

      ![Команда dotnet run](media/with-visual-studio-code/dotnetrun.png)

Вы можете просмотреть небольшие видеоматериалы с информацией о процессе настройки для [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), или [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).

## <a name="debug"></a>Отладка

1. Откройте файл *Program.cs*, щелкнув его. Когда вы в первый раз открываете файл C# в Visual Studio Code, в редакторе загружается [OmniSharp](http://www.omnisharp.net/).

    ![Откройте файл Program.cs](media/with-visual-studio-code/opencs.png)

2. Visual Studio Code предлагает добавить недостающие ресурсы для сборки и отладки приложения. Выберите ответ **Да**. 

    ![Предупреждение о недостающих ресурсах](media/with-visual-studio-code/missing-assets.png)

3. Чтобы открыть окно отладки, щелкните значок "Отладка" в меню слева.

    ![Откройте вкладку "Отладка"](media/with-visual-studio-code/opendebug.png)

4. Найдите зеленую стрелку в верхней части панели. Убедитесь, что в раскрывающемся списке рядом с ней выбран вариант `.NET Core Launch (console)`.

    ![Выбор .NET Core](media/with-visual-studio-code/selectcore.png)

5. Добавьте в проект точку останова, щелкнув **поле редактора** (пустое пространство слева от номеров строк) в строке 9.

    ![Установка точки останова](media/with-visual-studio-code/setbreakpoint.png)

6. Чтобы начать отладку, нажмите клавишу <kbd>F5</kbd> или щелкните зеленую стрелку. Отладчик останавливает выполнение программы, когда достигнет точки останова, которую вы только что установили.
    * Во время отладки вы можете просматривать локальные переменные в верхней левой области или в консоли отладки.

    ![Запуск и отладка](media/with-visual-studio-code/rundebug.png)

7. Выберите зеленую стрелку в верхней части, чтобы продолжить отладку, или выберите красный квадрат в верхней части, чтобы остановить процесс.

> [!TIP] 
> Дополнительные сведения и советы по отладке .NET Core в Visual Studio Code с помощью OmniSharp см. в разделе [Инструкции по настройке отладчика .NET Core](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).

## <a name="see-also"></a>См. также
[Настройка Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)   
[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Отладка в Visual Studio Code)
