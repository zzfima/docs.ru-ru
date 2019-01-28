---
title: Как выполнить Руководство по программированию на C#. Обработка исключений с помощью блока try-catch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
ms.openlocfilehash: 17b3be52bb89a1cf74bb8171ca937e434a8d94f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552532"
---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Обработка исключений с помощью блока try-catch
Блок [try-catch-](../../../csharp/language-reference/keywords/try-catch.md) предназначен для перехвата и обработки исключений, происходящих в исполняемом коде. Некоторые исключения могут обрабатываться в блоке `catch`, и проблема решается без повторного создания исключения. Но в большинстве случаев на этом этапе можно только проверить, что создано подходящее исключение.  
  
## <a name="example"></a>Пример  
 В этом примере <xref:System.IndexOutOfRangeException> не является наиболее подходящим исключением. Для данного метода больше подходит исключение <xref:System.ArgumentOutOfRangeException>, поскольку ошибка вызвана переданным методу аргументом `index`.  
  
 [!code-csharp[csProgGuideExceptions#5](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-handle-an-exception-using-try-catch_1.cs)]  
  
## <a name="comments"></a>Комментарии  
 Код, вызывающий исключение, находится в блоке `try`. Оператор `catch` добавляется сразу после него, чтобы обрабатывать исключение `IndexOutOfRangeException`, если оно происходит. Блок `catch` обрабатывает исключение `IndexOutOfRangeException` и вместо него вызывает более подходящее исключение `ArgumentOutOfRangeException`. Чтобы вызывающий объект получил максимально подробную информацию, рекомендуется указать исходное исключение в качестве значения <xref:System.Exception.InnerException%2A> нового исключения. Поскольку свойство <xref:System.Exception.InnerException%2A> [доступно только для чтения](../../../csharp/language-reference/keywords/readonly.md), его значение необходимо присваивать только в конструкторе нового исключения.  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/index.md)
- [Обработка исключений](../../../csharp/programming-guide/exceptions/exception-handling.md)
