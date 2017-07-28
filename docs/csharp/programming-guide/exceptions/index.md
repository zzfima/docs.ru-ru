---
title: "Исключения и обработка исключений (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#]
- exceptions [C#]
- C# language, exceptions
ms.assetid: 0001887f-4fa2-47e2-8034-2819477e2344
caps.latest.revision: 33
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
ms.openlocfilehash: e372cfa3239c39af86a29cda06b5817f0aeff0a2
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="exceptions-and-exception-handling-c-programming-guide"></a>Исключения и обработка исключений (Руководство по программированию в C#)
Функции обработки исключений в языке C# помогают вам справиться с непредвиденными или исключительными проблемами, которые возникают при выполнении программы. Обработка исключений использует ключевые слова `try`, `catch` и `finally` для действий, которые могут оказаться неудачными. Это позволяет обрабатывать ошибки так, как кажется разумным, а также правильно высвобождать ресурсы. Исключения могут создаваться средой выполнения (CLR), платформой .NET Framework, библиотеками сторонних поставщиков или кодом самого приложения. Чтобы создать исключение, используйте ключевое слово `throw`.  
  
 Во многих случаях исключение может создаваться не тем методом, который вызывается в вашем коде, а одним из последующих методов в стеке вызовов. В этом случае среда CLR разворачивает весь стек в поисках метода с блоком `catch` для исключений соответствующего типа, и выполняет первый обнаруженный блок `catch` подходящего вида. Если подходящий блок `catch` не будет обнаружен во всем стеке вызовов, среда CLR завершает процесс и выводит сообщение для пользователя.  
  
 В этом примере метод выполняет проверку деления на нуль и перехватывает ошибку. Если не использовать обработку исключений, такая программа завершит работу с ошибкой **DivideByZeroException was unhandled** (Исключение DivideByZero не обработано).  
  
 [!code-cs[csProgGuideExceptions#18](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exceptions-and-exception-handling_1.cs)]  
  
## <a name="exceptions-overview"></a>Общие сведения об исключениях  
 Исключения имеют следующие свойства.  
  
-   Исключения представляют собой типы, производные в конечном счете от `System.Exception`.  
  
-   Используйте блок `try` для выполнения таких инструкций, которые могут создавать исключения.  
  
-   Когда внутри такого блока `try` возникает исключение, поток управления переходит к первому подходящему обработчику исключений в стеке вызовов. В C# ключевое слово `catch` обозначает обработчик исключений.  
  
-   Если для созданного исключения не существует обработчиков, выполнение программы прекращается с сообщением об ошибке.  
  
-   Не перехватывайте исключение, если вы не намерены его обрабатывать с сохранением известного состояния приложения. Если вы перехватываете `System.Exception`, создайте его заново в конце блока `catch`, используя ключевое слово `throw`.  
  
-   Если блок `catch` определяет переменную исключения, ее можно использовать для получения дополнительных сведений о типе созданного исключения.  
  
-   Программа может явным образом создавать исключения с помощью ключевого слова `throw`.  
  
-   Объекты исключения содержат подробные сведения об ошибке, например состояние стека вызовов и текстовое описание ошибки.  
  
-   Код в блоке `finally` выполняется даже в том случае, если создано исключение. Используйте блок `finally`, чтобы высвободить ресурсы, например закрыть потоки и файлы, которые были открыты внутри блока `try`.  
  
-   Управляемые исключения реализованы в платформе .NET Framework на основе структурированного механизма обработки исключений Win32. Дополнительные сведения см. в статьях [Structured Exception Handling (C/C++)](/cpp/cpp/structured-exception-handling-c-cpp) (Структурированная обработка исключений в C и C++) и [A Crash Course on the Depths of Win32 Structured Exception Handling](http://go.microsoft.com/fwlink/?LinkId=119654) (Интенсивное погружение в структурированную обработку исключений на платформе Win32).  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения об исключениях и обработке исключений вы найдете в следующих статьях.  
  
-   [Использование исключений](../../../csharp/programming-guide/exceptions/using-exceptions.md)  
  
-   [Обработка исключений](../../../csharp/programming-guide/exceptions/exception-handling.md)  
  
-   [Создание и порождение исключений](../../../csharp/programming-guide/exceptions/creating-and-throwing-exceptions.md)  
  
-   [Исключения, создаваемые компилятором](../../../csharp/programming-guide/exceptions/compiler-generated-exceptions.md)  
  
-   [Практическое руководство. Обработка исключений с помощью блока try-catch (Руководство по программированию на C#)](../../../csharp/programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md)  
  
-   [Практическое руководство. Выполнение кода очистки с использованием блока finally](../../../csharp/programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.SystemException>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C#](../../../csharp/language-reference/keywords/index.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [Исключения](../../../standard/exceptions/index.md)   
 [Иерархия исключений](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b)   
 [Создание надежного кода .NET](http://go.microsoft.com/fwlink/?LinkId=112400)   
 [Минидампы для определенных исключений](http://go.microsoft.com/fwlink/?LinkId=112408)

