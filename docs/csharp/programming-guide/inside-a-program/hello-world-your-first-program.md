---
title: Руководство по программированию на C#. Создание первой программы Hello World
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 7ff65867f9f81118cad30852c439f8b3491bf1aa
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969730"
---
# <a name="hello-world----your-first-program-c-programming-guide"></a>Руководство по программированию на C#. Создание первой программы Hello World

В следующей процедуре создается версия традиционной программы "Hello World!" в C#. Программа отображает строку `Hello World!`

Дополнительные примеры основных понятий см. в разделе [Приступая к работе с Visual C# и Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-and-run-a-console-application"></a>Создание и запуск консольного приложения

1. Запустите Visual Studio.

2. В строке меню выберите **Файл**, **Создать**, **Проект**.

     Откроется диалоговое окно **Новый проект** .

3. Последовательно разверните узлы **Установленные**, **Шаблоны** и **Visual C#**, а затем выберите **Консольное приложение**.

4. В текстовом поле **Имя** введите имя проекта и нажмите кнопку **ОК**.

     В **обозревателе решений** появится новый проект.

5. Если файл Program.cs не открыт в **редакторе кода**, откройте контекстное меню для **Program.cs** в **обозревателе решений** и нажмите кнопку **Просмотреть код**.

6. Замените содержимое Program.cs кодом из этого примера.

     [!code-csharp[csProgGuide#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#21)]

7. Нажмите клавишу F5, чтобы запустить проект. Откроется окно командной строки, содержащее строку `Hello World!`

Далее рассматриваются важные части этой программы.

## <a name="comments"></a>Комментарии

Первая строка содержит комментарий. Символы `//` преобразуют остальную часть строки в комментарий.

 [!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

Вы можете также закомментировать блок текста, заключив его между символами `/*` и `*/`. Эти действия показаны в следующем примере.

 [!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

## <a name="main-method"></a>Main - метод

Консольное приложение C# должно содержать метод `Main`, в котором начинается и заканчивается управление. В методе `Main` создаются объекты и выполняются другие методы.

Метод `Main` является [статическим](../../../csharp/language-reference/keywords/static.md) методом, расположенным внутри класса или структуры. В предыдущем примере "Hello World!" он размещается в классе с именем `Hello`. Вы можете объявить метод `Main` одним из следующих способов.

- Он может возвращать значение `void`.

     [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- Он также может возвращать целое число.

     [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- С любым из типов возвращаемых значений он может принимать аргументы.

     [!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

     - или -

     [!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

Параметр `args` метода `Main` является массивом значений типа `string`, который содержит аргументы командной строки, используемые для вызова программы. В отличие от C++, массив не содержит имя исполняемого файла (EXE).

Дополнительные сведения об использовании командной строки см. в примерах в описании [Main() и аргументов командной строки](../../../csharp/programming-guide/main-and-command-args/index.md) и практическом руководстве по [ созданию и использованию сборок с помощью командной строки](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).

Вызов <xref:System.Console.ReadKey%2A> в конце метода `Main` предотвращает закрытие окна консоли, чтобы вы успели прочитать выходные данные, когда запускаете программу в режиме отладки с помощью клавиши F5.

## <a name="input-and-output"></a>Ввод и вывод

Программы на C#, как правило, используют службы ввода-вывода, предоставляемые библиотекой времени выполнения в .NET Framework. Инструкция `System.Console.WriteLine("Hello World!");` использует метод <xref:System.Console.WriteLine%2A>. Это один из методов вывода класса <xref:System.Console> в библиотеке времени выполнения. Он отображает свой строковый параметр в стандартном потоке вывода, за которым следует новая строка. Существуют и другие методы <xref:System.Console> для разных операций ввода и вывода. Если вы добавите в начало программы директиву `using System;`, классы и методы <xref:System> можно использовать напрямую, не указывая их полные имена. Например, можно вызвать `Console.WriteLine` вместо `System.Console.WriteLine`:

 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

 [!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

Дополнительные сведения о методах ввода-вывода см. в описании <xref:System.IO>.

## <a name="command-line-compilation-and-execution"></a>Компиляция и выполнение из командной строки

Программу "Hello World!" можно скомпилировать, используя командную строку вместо интегрированной среды разработки Visual Studio.

### <a name="to-compile-and-run-from-a-command-prompt"></a>Компиляция и выполнение программы из командной строки

1. Вставьте код из предыдущей процедуры в любой текстовый редактор и сохраните файл как текстовый файл. Назовите файл `Hello.cs`. Для файлов исходного кода C# используется расширение `.cs`.

2. Выполните одно из следующих действий, чтобы открыть окно командной строки.

    - В меню **Пуск** Windows 10 введите `Developer Command Prompt` в строке поиска, а затем выберите пункт **Командная строка разработчика для VS 2017**.

         Откроется окно "Командная строка разработчика".

    - В Windows 7 откройте меню **Пуск**, разверните папку текущей версии Visual Studio, откройте контекстное меню **Инструменты Visual Studio** и выберите пункт **Командная строка разработчика для VS 2017**.

         Откроется окно "Командная строка разработчика".

    - Включите сборки из командной строки из стандартного окна командной строки.

         См. практическое руководство по [ настройке переменных среды для командной строки Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).

3. В окне командной строки перейдите к папке, содержащей файл `Hello.cs`.

4. Введите следующую команду для компиляции `Hello.cs`.

     `csc Hello.cs`

     Если для программы не выдаются ошибки компиляции, создается исполняемый файл с именем `Hello.exe`.

5. В окне командной строки введите следующую команду, чтобы запустить программу:

     `Hello`

 Дополнительные сведения о компиляторе C# и его параметрах см. в разделе [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md).

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Структура программы C#](../../../csharp/programming-guide/inside-a-program/index.md)
- [Строки](../../../csharp/programming-guide/strings/index.md)
- [Примеры и руководства](../../../samples-and-tutorials/index.md)
- [Справочник по C#](../../../csharp/language-reference/index.md)
- [Main() и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/index.md)
- [Начало работы с Visual C# и Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)