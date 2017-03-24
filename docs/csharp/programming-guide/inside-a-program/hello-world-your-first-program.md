---
title: "Hello World – Создаем первую программу (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "get-started-article"
f1_keywords: 
  - "cs.program"
  - "vs.csharp.startpage.firstapplication"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "примеры [C#], Hello World"
  - "Hello World - пример [C#]"
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
caps.latest.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 39
---
# Hello World – Создаем первую программу (Руководство по программированию на C#)
В следующей процедуре создается версия для C\# традиционной программы "Hello World".  Программа отображает строку `Hello World!`  
  
 Дополнительные примеры вводных концепций см. в разделе [Начало работы с Visual C\# и Visual Basic](/visual-studio/ide/getting-started-with-visual-csharp-and-visual-basic).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Создание и запуск консольного приложения  
  
1.  Запустите Visual Studio.  
  
2.  В меню **Файл** выберите **Создать**, **Проект**.  
  
     Откроется диалоговое окно **Новый проект**.  
  
3.  Разверните узел **Установленные**, разверните **Шаблоны**, разверните **Visual C\#**, а затем выберите **Консольное приложение**.  
  
4.  В поле **Имя** введите имя для проекта и нажмите кнопку **ОК**.  
  
     В **обозревателе решений** появится новый проект.  
  
5.  Если файл Program.cs не открыт в **редакторе кода**, откройте контекстное меню **Program.cs** в **обозревателе решений**, а затем нажмите кнопку **Просмотреть код**.  
  
6.  Заменяет содержимое файла Program.cs на следующий код.  
  
     [!code-cs[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]  
  
7.  Нажмите клавишу F5, чтобы запустить проект.  Появляется окно командной строки, содержащее строку `Hello World!`  
  
 Далее изучаются важные составляющие этой программы.  
  
## Комментарии  
 Первая строка содержит комментарий.  Символы `//` преобразуют остальную часть строки в комментарий.  
  
 [!code-cs[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]  
  
 Можно также сделать комментарием блок текста, окружив его символами `/*` и `*/`.  Это показано в следующем примере.  
  
 [!code-cs[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]  
  
## Метод Main  
 Консольное приложение C\# должно содержать метод `Main`, в котором начинается и заканчивается управление.  В методе `Main` создаются объекты и выполняются другие методы.  
  
 Метод `Main` является статическим методом [статический](../../../csharp/language-reference/keywords/static.md), расположенным внутри класса или структуры.  В предыдущем примере "Hello World\!" он расположен в классе с именем `Hello`.  Метод `Main` можно объявить одним из следующих способов:  
  
-   Он возвращает значение `void`.  
  
     [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]  
  
-   Также может возвращаться целое значение.  
  
     [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]  
  
-   С обоими возвращаемыми типами он может принимать следующие аргументы.  
  
     [!code-cs[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]  
  
     \-или\-  
  
     [!code-cs[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]  
  
 Параметр метода `Main` `args` является массивом значений типа `string`, который содержит аргументы командной строки, используемые для вызова программы.  В отличие от C\+\+, массив не содержит имени исполняемого \(EXE\) файла.  
  
 Дополнительные сведения об использовании аргументов командной строки можно получить из примеров, приведенных в разделе [Main\(\) и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md) и [Практическое руководство. Создание и использование сборок с помощью командной строки](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Вызов метода <xref:System.Console.ReadKey%2A> в конце метода `Main` предотвращает закрытие окна консоли, чтобы вывод при выполнении программы в отладочном режиме можно было прочесть нажатием клавиши F5.  
  
## Ввод и вывод  
 Программы на C\#, как правило, используют службы ввода\/вывода, предоставляемые библиотекой времени выполнения в .NET Framework.  Оператор `System.Console.WriteLine("Hello World!");` использует метод <xref:System.Console.WriteLine%2A>.  Это один из методов вывода класса <xref:System.Console> в библиотеке времени выполнения.  Он выводит свои строковые параметры в стандартном потоке вывода, за которым следует новая строка.  Другие методы <xref:System.Console> используются для разных операций ввода и вывода.  Если в начало программы поместить директиву `using System;`, классы <xref:System> и методы можно будет использовать напрямую без указания их полного имени.  Например, можно вызвать `Console.WriteLine` вместо `System.Console.WriteLine`:  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]  
  
 [!code-cs[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]  
  
 Дополнительные сведения о методах ввода\/вывода см. в разделе <xref:System.IO>.  
  
## Компиляция и выполнение в командной строке  
 Программу "Hello World\!" можно скомпилировать, используя командную строку, а не интегрированную среду разработки \(IDE\) Visual Studio.  
  
#### Компиляция и запуск из командной строки  
  
1.  Вставьте код из предыдущей процедуры в любой текстовый редактор и сохраните его как текстовый файл.  Назовите файл `Hello.cs`.  Файл исходного кода C\# имеет расширение `.cs`.  
  
2.  Выполните один из следующих шагов, чтобы открыть окно командной строки.  
  
    -   В Windows 8 на экране **Запуск** найдите `Командная строка разработчика`, а затем коснитесь или выберите **Командная строка разработчика для VS2012**.  
  
         Появится окно командной строки разработчика.  
  
    -   В Windows 7 откройте меню **Запуск**, разверните папку для текущей версии Visual Studio, откройте контекстное меню для **Visual Studio**, а затем выберите **Командная строка разработчика для VS2012**.  
  
         Появится окно командной строки разработчика.  
  
    -   Включение сборки из командной строки из стандартного окна командной строки.  
  
         Дополнительные сведения см. в разделе [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
3.  В окне командной строки перейдите в папку, содержащую файл `Hello.cs`.  
  
4.  Чтобы скомпилировать `Hello.cs`, введите следующую команду.  
  
     `csc Hello.cs`  
  
     Если программа не содержит ошибок компиляции, то создается исполняемый файл с именем `Hello.exe`.  
  
5.  Введите в командной строке следующую команду, чтобы запустить программу:  
  
     `Hello`  
  
 Дополнительные сведения о компиляторе C\# и его параметрах см. в разделе [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md).  
  
## Важная глава книги  
 [При создании программы C\#](http://go.microsoft.com/fwlink/?LinkId=221227) в [Начало работы с Visual C\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Структура программы C\#](../../../csharp/programming-guide/inside-a-program/index.md)   
 [Строки](../../../csharp/programming-guide/strings/index.md)   
 [\<paveover\>C\# Sample Applications](http://msdn.microsoft.com/ru-ru/9a9d7aaa-51d3-4224-b564-95409b0f3e15)   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Main\(\) и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Начало работы с Visual C\# и Visual Basic](/visual-studio/ide/getting-started-with-visual-csharp-and-visual-basic)