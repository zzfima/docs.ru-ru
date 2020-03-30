---
title: Руководство по программированию на C#. Значения, возвращаемые методом Main()
ms.date: 08/02/2017
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: 3d97ab2b3f53179cb184f2ad3944ea29ff5566a2
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345127"
---
# <a name="main-return-values-c-programming-guide"></a>Значения, возвращаемые методом Main() (Руководство по программированию на C#)

Метод `Main` может возвращать значение `void`:

 [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

Он также может возвращать значение типа `int`:

 [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

Если значение, возвращаемое методом `Main`, не используется, то указание в качестве возвращаемого типа `void` несколько упрощает код. Однако возврат целого значения позволяет программе передавать информацию о своем состоянии другим программам и скриптам, которые вызывают исполняемый файл. Возвращаемое значение `Main` рассматривается как код выхода процесса. Если `void` возвращается из `Main`, код завершения будет неявно задан как `0`. В приведенном ниже примере показано, как получить доступ к значению, возвращаемому методом `Main`.

## <a name="example"></a>Пример

В этом примере используются средства командной строки [.NET Core](../../../core/index.yml). Если вы не знакомы со средствами командной строки .NET Core, можете обратиться к [этому руководству по началу работы](../../../core/tutorials/cli-create-console-app.md).

Измените метод `Main` в файле *program.cs* следующим образом:

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

При запуске программы в Windows значение, возвращаемое функцией `Main`, сохраняется в переменной среды. Эту переменную можно получить из пакетного файла с помощью команды `ERRORLEVEL` или в PowerShell с помощью команды `$LastExitCode`.

Для сборки приложения можно выполнить команду `dotnet build` [интерфейса командной строки .NET](../../../core/tools/dotnet.md).

Затем создайте сценарий PowerShell для запуска приложения и отображения результата. Вставьте следующий код в текстовый файл и сохраните его под именем `test.ps1` в папке проекта. Запустите сценарий PowerShell, набрав команду `test.ps1` в командной строке PowerShell.

Так как код возвращает нулевое значение, пакетный файл сообщает об успехе. Но если изменить файл MainReturnValTest.cs, чтобы он возвращал ненулевое значение, и затем повторно скомпилировать программу, то при последующем выполнении сценария PowerShell будет выдано сообщение об ошибке.

```dotnetcli
dotnet run
```

```powershell
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a>Пример полученных результатов

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a>Значения, возвращаемые асинхронным методом main

Возвращаемые значения асинхронного метода main перемещают стандартный код, необходимый для вызова асинхронных методов в `Main`, в код, созданный компилятором. Ранее для вызова асинхронного кода и для запуска программы до завершения асинхронной операции приходилось использовать следующую конструкцию:

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

Теперь ее можно заменить на:

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

Преимущество нового синтаксиса состоит в том, что компилятор всегда формирует правильный код.

## <a name="compiler-generated-code"></a>Код, созданный компилятором

Если точка входа приложения возвращает `Task` или `Task<int>`, то компилятор создает новую точку входа, которая вызывает метод точки входа, объявленный в коде приложения. Предположим, что эта точка входа называется `$GeneratedMain`. В этом случае компилятор создает следующий код для этих точек входа:

- `static Task Main()` приводит к тому, что компилятор формирует эквивалент `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`
- `static Task Main(string[])` приводит к тому, что компилятор формирует эквивалент `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`
- `static Task<int> Main()` приводит к тому, что компилятор формирует эквивалент `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`
- `static Task<int> Main(string[])` приводит к тому, что компилятор формирует эквивалент `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`

> [!NOTE]
>Если бы в примерах использовался модификатор `async` метода `Main`, компилятор сформировал бы точно такой же код.

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Справочник по C#](../index.md)
- [Main() и аргументы командной строки](index.md)
- [Отображение аргументов командной строки](./how-to-display-command-line-arguments.md)
