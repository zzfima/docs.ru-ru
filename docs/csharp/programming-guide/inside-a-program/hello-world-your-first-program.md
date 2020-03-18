---
title: Руководство по программированию на C#. Создание первой программы Hello World с помощью Visual Studio в Windows или Mac
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 910fa4af1b4e45ce627b589a06910dc168490047
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712147"
---
# <a name="hello-world----your-first-program"></a>Hello World — создаем первую программу

В этой статье вы будете использовать Visual Studio для создания традиционной программы "Hello World!" в C#. Visual Studio — это профессиональная интегрированная среда разработки (IDE) с множеством функций, предназначенных для разработки в среде .NET. Для создания этой программы вы будете использовать лишь некоторые функции Visual Studio. См. дополнительные сведения о [начале работы с Visual C#](/visualstudio/ide/quickstart-csharp-console).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a>Создание приложения

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[Windows](#tab/windows)

Запустите среду Visual Studio. В Windows вы увидите следующее изображение:

![Экран приветствия Visual Studio в Windows](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

Выберите **Создать проект** в правом нижнем углу изображения. В Visual Studio отображается диалоговое окно **Новый проект**:

![Экран нового проекта Visual Studio в Windows](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> Если вы запустили Visual Studio впервые, список **Последние шаблоны проектов** будет пустым.

В диалоговом окне "Новый проект" выберите "Консольное приложение (.NET Core)" и нажмите кнопку **Далее**. Присвойте проекту имя, например "HelloWorld", а затем нажмите кнопку **Создать**.

Проект открывается в Visual Studio. Он уже является базовым примером Hello, World! Нажмите клавиши `Ctrl` + `F5` для запуска проекта. Visual Studio выполняет сборку проекта, преобразуя исходный код в исполняемый файл. Затем запускается командное окно, запускающее новое приложение. В окне должен отображаться следующий текст:

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

Нажмите любую клавишу, чтобы закрыть окно.

# <a name="macos"></a>[macOS](#tab/macos)

Запустите Visual Studio для Mac. В Mac вы увидите следующее изображение:

![Экран приветствия Visual Studio в Mac](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> Если вы запустили Visual Studio для Mac впервые, список **Последние проекты** будет пустым.

Выберите **Создать** в правом верхнем углу изображения. В Visual Studio для Mac отображается диалоговое окно **Новый проект**:

![Экран нового проекта Visual Studio в Mac](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

В диалоговом окне "Новый проект" выберите ".NET Core" и "Консольное приложение" и затем нажмите кнопку **Далее**. Вам потребуется выбрать целевую платформу. Значение по умолчанию подходит, поэтому нажмите кнопку "Далее". Присвойте проекту имя, например "HelloWorld", а затем нажмите кнопку **Создать**. Вы можете использовать расположение проекта по умолчанию. Не добавляйте этот проект в систему управления версиями.

Проект открывается в Visual Studio для Mac. Он уже является базовым примером Hello, World! Нажмите клавиши `Ctrl` + `Fn` + `F5` для запуска проекта. Visual Studio для Mac выполняет сборку проекта, преобразуя исходный код в исполняемый файл. Затем запускается командное окно, запускающее новое приложение. В окне должен отображаться следующий текст:

```console
Hello World!

Press any key to close this window . . .
```

Нажмите клавишу, чтобы завершить сеанс.

---

## <a name="elements-of-a-c-program"></a>Элементы программы C#

Давайте рассмотрим важные части этой программы. Первая строка содержит комментарий. Символы `//` преобразуют остальную часть строки в комментарий.

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

Вы можете также закомментировать блок текста, заключив его между символами `/*` и `*/`. Это показано в следующем примере.

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

Консольное приложение C# должно содержать метод `Main`, в котором начинается и заканчивается управление. В методе `Main` создаются объекты и выполняются другие методы.

Метод `Main` является [статическим](../../language-reference/keywords/static.md) методом, расположенным внутри класса или структуры. В предыдущем примере "Hello World!" он размещается в классе с именем `Hello`. Вы можете объявить метод `Main` одним из следующих способов.

- Он может возвращать значение `void`. Это означает, что программа не возвращает значение.

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- Он также может возвращать целое число. Данное целое число — это **код выхода** для приложения.

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- С любым из типов возвращаемых значений он может принимать аргументы.

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

-или-

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

Параметр `Main` метода `args` является массивом значений типа `string`, который содержит аргументы командной строки, используемые для вызова программы.

Дополнительные сведения об использовании аргументов командной строки см. в примерах в разделе [Main() и аргументы командной строки](../main-and-command-args/index.md).

## <a name="input-and-output"></a>Входные и выходные данные

Программы на C#, как правило, используют службы ввода-вывода, предоставляемые библиотекой времени выполнения в .NET Framework. Инструкция `System.Console.WriteLine("Hello World!");` использует метод <xref:System.Console.WriteLine%2A>. Это один из методов вывода класса <xref:System.Console> в библиотеке времени выполнения. Он отображает свой строковый параметр в стандартном потоке вывода, за которым следует новая строка. Существуют и другие методы <xref:System.Console> для разных операций ввода и вывода. Если вы добавите в начало программы директиву `using System;`, классы и методы <xref:System> можно использовать напрямую, не указывая их полные имена. Например, можно вызвать `Console.WriteLine` вместо `System.Console.WriteLine`:

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

Дополнительные сведения о методах ввода-вывода см. в описании <xref:System.IO>.

## <a name="see-also"></a>См. также раздел

- [Руководство по программированию на C#](../index.md)
- [Примеры и руководства](../../../samples-and-tutorials/index.md)
- [Main() и аргументы командной строки](../main-and-command-args/index.md)
- [Начало работы с Visual C#](/visualstudio/ide/quickstart-csharp-console)
