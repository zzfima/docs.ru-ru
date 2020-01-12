---
title: Начало работы с C# и Visual Studio Code
description: Узнайте, как создать и отладить в Visual Studio Code свое первое приложение .NET Core на языке C#.
author: kendrahavens
ms.date: 12/05/2018
ms.openlocfilehash: fdf26d67ca06ffb5ae9f8c12aa29819280770d5c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715310"
---
# <a name="get-started-with-c-and-visual-studio-code"></a>Начало работы с C# и Visual Studio Code

.NET Core предcтавляет собой быструю модульную платформу для создания приложений, работающих на ОС Windows, Linux и macOS. Visual Studio Code с расширением C# позволяет эффективно работать с кодом, а также обеспечивает полную поддержку IntelliSense (интеллектуальное завершение кода) и отладки для языка C#.

## <a name="prerequisites"></a>Предварительные требования

1. Установите [Visual Studio Code](https://code.visualstudio.com/).
2. Установите [пакета SDK для .NET Core](https://dotnet.microsoft.com/download).
3. Установите [расширение C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) для Visual Studio Code. См. дополнительные сведения об [установке расширений Visual Studio Code из Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).

## <a name="hello-world"></a>Hello World

Давайте начнем с создания простой программы Hello World для .NET Core.

1. Откройте проект.

    - Откройте Visual Studio Code.
    - Щелкните значок обозревателя в расположенном слева меню, затем щелкните**Открыть папку**.
    - Выберите **Файл** > **Открыть папку** в главном меню, чтобы открыть папку, в которой вы хотите разместить проект C#, и щелкните **Выбрать папку**. В нашем примере мы создаем для проекта папку с именем *HelloWorld*.

      ![Кнопка "Открыть папку" в Visual Studio Code](media/with-visual-studio-code/vs-code-open-folder.png)

2. Инициализируйте проект C#.

    - Откройте в Visual Studio Code интегрированный терминал, выбрав **Просмотр** > **Интегрированный терминал** в главном меню.
    - В окне терминала введите `dotnet new console`.
    - Эта команда создает в выбранной папке файл *Program.cs* с уже готовой простой программой Hello World, а также файл проекта C# с именем *HelloWorld.csproj*.

      ![Команда dotnet new](media/with-visual-studio-code/dotnet-new-command.png)

3. Выполните разрешение для средств сборки:

    - Для **.NET Core 1.x** введите `dotnet restore`. Команда `dotnet restore` предоставляет доступ к пакетам .NET Core, которые необходимы для сборки этого проекта.

      ![Команда dotnet restore](media/with-visual-studio-code/dotnet-restore-command.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. Запустите программу Hello World.

    - Введите `dotnet run`.

      ![Команда dotnet run](media/with-visual-studio-code/dotnet-run-command.png)

Вы можете просмотреть небольшие видеоматериалы с информацией о процессе настройки для [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), или [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).

## <a name="debug"></a>Отладка

1. Откройте файл *Program.cs*, щелкнув его. Когда вы в первый раз открываете файл C# в Visual Studio Code, в редакторе загружается [OmniSharp](https://www.omnisharp.net/).

    ![Откройте файл Program.cs](media/with-visual-studio-code/open-program-cs.png)

2. Visual Studio Code предлагает добавить недостающие ресурсы для сборки и отладки приложения. Выберите ответ **Да**.

    ![Предупреждение о недостающих ресурсах](media/with-visual-studio-code/missing-assets.png)

3. Чтобы открыть окно отладки, щелкните значок "Отладка" в меню слева.

    ![Откройте вкладку "Отладка" в Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

4. Найдите зеленую стрелку в верхней части панели. Убедитесь, что в раскрывающемся списке рядом с ней выбран вариант **Запуск .NET Core (консоль)** .

    ![Выбор .NET Core в Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

5. Добавьте в проект точку останова, щелкнув **поле редактора** (пустое пространство слева от номеров строк) в строке 9, или переместите курсор текста в строку 9 в редакторе и нажмите клавишу <kbd>F9</kbd>.

    ![Установка точки останова](media/with-visual-studio-code/set-breakpoint-vs-code.png)

6. Чтобы начать отладку, нажмите клавишу <kbd>F5</kbd> или щелкните зеленую стрелку. Отладчик останавливает выполнение программы, когда достигнет точки останова, которую вы только что установили.
    - Во время отладки вы можете просматривать локальные переменные в верхней левой области или в консоли отладки.

7. Выберите синюю стрелку в верхней части, чтобы продолжить отладку, или выберите красный квадрат в верхней части, чтобы остановить процесс.

    ![Запуск и отладка в Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> Дополнительные сведения и советы по отладке .NET Core в Visual Studio Code с помощью OmniSharp см. в разделе [Инструкции по настройке отладчика .NET Core](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).

## <a name="add-a-class"></a>Добавление класса

1. Чтобы добавить новый класс, щелкните правой кнопкой мыши в обозревателе VSCode и выберите **Новый файл**. Так вы добавите новый файл в папку, открытую в VSCode.
2. Назовите файл *MyClass.cs*. Необходимо сохранить его с расширением `.cs`, чтобы он распознавался как файл С#.
3. Добавьте приведенный ниже код для создания класса. Включите правильное пространство имен, на которое будет создана ссылка из файла *Program.cs*:

    ``` csharp
    using System;

    namespace HelloWorld
    {
        public class MyClass
        {
            public string ReturnMessage()
            {
                return "Happy coding!";
            }
        }
    }
    ```

4. Вызовите новый класс из метода main в *Program.cs*, добавив приведенный ниже код:

    ```csharp
    using System;
    
    namespace HelloWorld
    {
        class Program
        {
            static void Main(string[] args)
            {
                var c1 = new MyClass();
                Console.WriteLine($"Hello World! {c1.ReturnMessage()}");
            }
        }
    }
    ```

5. Сохраните изменения и снова запустите программу. Должно отобразиться новое сообщение с добавленной строкой.

    ```console
    > dotnet run
    Hello World! Happy coding!
    ```

## <a name="faq"></a>часто задаваемые вопросы

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a>Мне не хватает ресурсов для выполнения сборки и отладки C# в Visual Studio Code. Отладчик выдает сообщение: "Конфигурация отсутствует".

Ресурсы для сборки и отладки можно создать с помощью расширения Visual Studio Code C#. Visual Studio Code предложит создать эти ресурсы при первом открытии проекта C#. Если вы не создали ресурсы, вы все равно сможете выполнить эту команду. Для этого откройте палитру команд (**Вид > Палитра команд**) и введите ">.NET: Generate Assets for Build and Debug" (.NET: создать ресурсы для сборки и отладки). После этого будут созданы необходимые файлы конфигурации *.vscode*, *launch.json* и *tasks.json*.

## <a name="see-also"></a>См. также

- [Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) (Настройка Visual Studio Code)
- [Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Отладка в Visual Studio Code)
