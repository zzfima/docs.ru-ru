---
title: "Hello World — создаем первую программу (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: get-started-article
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
dev_langs:
- CSharp
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 7e33ed084c560470a486ebbb25035a59ddc18565
ms.openlocfilehash: 21abcf70cce2d6c9052629ce60d08e9ec6ac16e7
ms.contentlocale: ru-ru
ms.lasthandoff: 03/31/2017

---
# <a name="hello-world----your-first-program-c-programming-guide"></a>Hello World – Создаем первую программу (Руководство по программированию на C#)
В следующей процедуре создается версия традиционной программы "Hello World!" в C#. Программа отображает строку `Hello World!`  
  
 Дополнительные примеры основных понятий см. в разделе [Приступая к работе с Visual C# и Visual Basic](https://docs.microsoft.com/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-and-run-a-console-application"></a>Создание и запуск консольного приложения  
  
1.  Запустите Visual Studio.  
  
2.  В строке меню выберите **Файл**, **Создать**, **Проект**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
3.  Последовательно разверните узлы **Установленные**, **Шаблоны** и **Visual C#**, а затем выберите **Консольное приложение**.  
  
4.  В текстовом поле **Имя** введите имя проекта и нажмите кнопку **ОК**.  
  
     В **обозревателе решений** появится новый проект.  
  
5.  Если файл Program.cs не открыт в **редакторе кода**, откройте контекстное меню для **Program.cs** в **обозревателе решений** и нажмите кнопку **Просмотреть код**.  
  
6.  Замените содержимое Program.cs кодом из этого примера.  
  
     [!code-cs[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]  
  
7.  Нажмите клавишу F5, чтобы запустить проект. Откроется окно командной строки, содержащее строку `Hello World!`  
  
 Далее рассматриваются важные части этой программы.  
  
## <a name="comments"></a>Комментарии  
 Первая строка содержит комментарий. Символы `//` преобразуют остальную часть строки в комментарий.  
  
 [!code-cs[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]  
  
 Вы можете также закомментировать блок текста, заключив его между символами `/*` и `*/`. Эти действия показаны в следующем примере.  
  
 [!code-cs[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]  
  
## <a name="main-method"></a>Метод Main  
 Консольное приложение C# должно содержать метод `Main`, в котором начинается и заканчивается управление. В методе `Main` создаются объекты и выполняются другие методы.  
  
 Метод `Main` является [статическим](../../../csharp/language-reference/keywords/static.md) методом, расположенным внутри класса или структуры. В предыдущем примере "Hello World!" он размещается в классе с именем `Hello`. Вы можете объявить метод `Main` одним из следующих способов.  
  
-   Он может возвращать значение `void`.  
  
     [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]  
  
-   Он также может возвращать целое число.  
  
     [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]  
  
-   С любым из типов возвращаемых значений он может принимать аргументы.  
  
     [!code-cs[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]  
  
     -или-  
  
     [!code-cs[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]  
  
 Параметр `args` метода `Main` является массивом значений типа `string`, который содержит аргументы командной строки, используемые для вызова программы. В отличие от C++, массив не содержит имя исполняемого файла (EXE).  
  
 Дополнительные сведения об использовании командной строки см. в примерах в разделах [Main() и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/index.md) и [Практическое руководство. Создание и использование сборок с помощью командной строки](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).  
  
 Вызов <xref:System.Console.ReadKey%2A> в конце метода `Main` предотвращает закрытие окна консоли, прежде чем вы сможете прочитать выходные данные, при запуске программы в режиме отладки с помощью клавиши F5.  
  
## <a name="input-and-output"></a>Ввод и вывод  
 Программы на C#, как правило, используют службы ввода-вывода, предоставляемые библиотекой времени выполнения в .NET Framework. Инструкция `System.Console.WriteLine("Hello World!");` использует метод <xref:System.Console.WriteLine%2A>. Это один из методов вывода класса <xref:System.Console> в библиотеке времени выполнения. Он отображает свой строковый параметр в стандартном потоке вывода, за которым следует новая строка. Другие методы <xref:System.Console> доступны для различных операций ввода и вывода. При включении директивы `using System;` в начало программы классы и методы <xref:System> можно использовать непосредственно без указания их полного имени. Например, можно вызвать `Console.WriteLine` вместо `System.Console.WriteLine`:  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]  
  
 [!code-cs[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]  
  
 Дополнительные сведения о методах ввода-вывода см. в разделе <xref:System.IO>.  
  
## <a name="command-line-compilation-and-execution"></a>Компиляция и выполнение из командной строки  
 Программу "Hello World!" можно скомпилировать, используя командную строку вместо интегрированной среды разработки Visual Studio.  
  
#### <a name="to-compile-and-run-from-a-command-prompt"></a>Компиляция и выполнение программы из командной строки  
  
1.  Вставьте код из предыдущей процедуры в любой текстовый редактор и сохраните файл как текстовый файл. Назовите файл `Hello.cs`. Для файлов исходного кода C# используется расширение `.cs`.  
  
2.  Выполните одно из следующих действий, чтобы открыть окно командной строки.  
  
    -   В Windows 8 на **начальном** экране выполните поиск по термину `Developer Command Prompt`, а затем выберите **Командная строка разработчика для VS2012**.  
  
         Откроется окно "Командная строка разработчика".  
  
    -   В Windows 7 откройте меню **Пуск**, разверните папку для текущей версии Visual Studio, откройте контекстное меню для **Инструменты Visual Studio** и выберите **Командная строка разработчика для VS2012**.  
  
         Откроется окно "Командная строка разработчика".  
  
    -   Включите сборки из командной строки из стандартного окна командной строки.  
  
         См. раздел [Практическое руководство. Настройка переменных среды для командной строки Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
3.  В окне командной строки перейдите к папке, содержащей файл `Hello.cs`.  
  
4.  Введите следующую команду для компиляции `Hello.cs`.  
  
     `csc Hello.cs`  
  
     Если для программы не выдаются ошибки компиляции, создается исполняемый файл с именем `Hello.exe`.  
  
5.  В окне командной строки введите следующую команду, чтобы запустить программу:  
  
     `Hello`  
  
 Дополнительные сведения о компиляторе C# и его параметрах см. в разделе [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md).
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Структура программы C#](../../../csharp/programming-guide/inside-a-program/index.md)   
 [Строки](../../../csharp/programming-guide/strings/index.md)   
 [\<paveover>Примеры приложений Visual C++](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Main() и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/index.md)   
 [Начало работы с Visual C# и Visual Basic](https://docs.microsoft.com/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)
