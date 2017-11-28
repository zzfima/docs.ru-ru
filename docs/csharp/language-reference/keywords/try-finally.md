---
title: "try-finally (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
caps.latest.revision: "25"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 927b851419f2c5245518ee39bf847cb1f1664917
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="try-finally-c-reference"></a>try-finally (Справочник по C#)
С помощью блока `finally` можно выполнить очистку всех ресурсов, выделенных в блоке [try](../../../csharp/language-reference/keywords/try-catch.md), и запускать код даже при возникновении исключения в блоке `try`. Как правило, операторы блока `finally` выполняются, когда элемент управления покидает оператор `try`. Передача управления может возникать в результате нормального выполнения, выполнения операторов `break`, `continue`, `goto` или `return` или распространения исключения из оператора `try`.  
  
 Внутри обработанного исключения гарантируется выполнение связанного блока `finally`. Однако если исключение не обработано, то выполнение блока `finally` зависит от того, как запускается операция развертывания исключения. Это, в свою очередь, зависит от способа настройки компьютера.
  
 Как правило, когда необработанное исключение приводит к завершению работы приложения, выполнение блока `finally` не имеет значения. Однако если в блоке `finally` есть операторы, которые необходимо запускать даже в такой ситуации, одним из решений является добавление блока `catch` в оператор `try`-`finally`. Кроме того, можно перехватить исключение, которое может создаваться в блоке `try` оператора `try`-`finally` выше в стеке вызовов. То есть можно перехватить исключение в методе, который вызывает метод, содержащий оператор `try`-`finally`, или в методе, который вызывает этот метод, или в любом методе в стеке вызовов. Если исключение не перехвачено, выполнение блока `finally` зависит от того, активирует ли операционная система операцию развертывания исключения.  
  
## <a name="example"></a>Пример  
 В следующем примере недопустимый оператор преобразования вызывает исключение `System.InvalidCastException`. Исключение не обрабатывается.  
  
 [!code-csharp[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]  
  
 В следующем примере исключение из метода `TryCast` перехватывается в методе выше в стеке вызовов.  
  
 [!code-csharp[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]  
  
 Дополнительные сведения о `finally` см. в разделе [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).  
  
 C# также содержит [оператор using](../../../csharp/language-reference/keywords/using-statement.md), который предоставляет аналогичную функциональность для объектов <xref:System.IDisposable> в удобном синтаксисе.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Операторы try, throw и catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)  
 [Операторы обработки исключений](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
 [throw](../../../csharp/language-reference/keywords/throw.md)  
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)  
 [Практическое руководство. Явное создание исключений](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
