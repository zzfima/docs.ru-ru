---
title: "Main() и аргументы командной строки (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
caps.latest.revision: 30
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1b2950f7718cda66b545935229a64850449850d0
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="main-and-command-line-arguments-c-programming-guide"></a>Main() и аргументы командной строки (Руководство по программированию на C#)
Метод `Main` является точкой входа консольного или оконного приложения C#. (Библиотекам и службам точка входа в виде метода `Main` не требуется.) Когда приложение запускается, первым вызывается именно метод `Main`.  
  
 В программе на C# может существовать только одна точка входа. Если у вас есть несколько классов с методом `Main`, программу нужно компилировать с параметром **/main**, чтобы указать, какой из методов `Main` будет использоваться в качестве точки входа. Дополнительные сведения см. в разделе [/main (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).  
  
 [!code-cs[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]  
  
## <a name="overview"></a>Обзор  
  
-   Метод `Main` является точкой входа для программы .exe. Здесь начинается и заканчивается управление программой.  
  
-   `Main` объявляется внутри класса или структуры. `Main` должен являться [статическим](../../../csharp/language-reference/keywords/static.md) и не может быть [открытым](../../../csharp/language-reference/keywords/public.md). (В предыдущем примере он по умолчанию получает уровень доступа [private](../../../csharp/language-reference/keywords/private.md) (закрытый).) Класс или структура, в которой он объявлен, не обязаны быть статическими.  
  
-   `Main` может возвращать значение типа `void` или `int`.  
  
-   Метод `Main` может быть объявлен с параметром `string[]`, который содержит аргументы командной строки, или без него. Когда вы используете [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] для создания приложений Windows Forms, вы можете добавить параметр вручную либо воспользоваться классом <xref:System.Environment> для получения аргументов командной строки. Параметры считываются как аргументы командной строки, индексы которых начинаются с нуля. В отличие от C и C++, имя программы не рассматривается как первый аргумент командной строки.  
  
## <a name="in-this-section"></a>Содержание  
  
-   [Аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)  
  
-   [Практическое руководство. Отображение аргументов командной строки](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
  
-   [Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
  
-   [Значения, возвращаемые методом main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  (Сборка из командной строки с помощью csc.exe)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Methods (C# Programming Guide)](../../../csharp/programming-guide/classes-and-structs/methods.md)  (Методы (руководство по программированию на C#)  
 [Inside a C# Program](../../../csharp/programming-guide/inside-a-program/index.md)  (Структура программы C#)  
 [\<paveover>Примеры приложений на C#](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)

