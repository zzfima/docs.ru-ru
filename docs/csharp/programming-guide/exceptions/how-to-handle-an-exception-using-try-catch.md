---
title: "Практическое руководство. Обработка исключений с помощью блока try-catch (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
caps.latest.revision: 14
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 10eac61f4b9bb186d28044862ebc7273c6eb07b2
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>Практическое руководство. Обработка исключений с помощью блока try-catch (Руководство по программированию на C#)
Блок [try-catch-](../../../csharp/language-reference/keywords/try-catch.md) предназначен для перехвата и обработки исключений, происходящих в исполняемом коде. Некоторые исключения могут обрабатываться в блоке `catch`, и проблема решается без повторного создания исключения. Но в большинстве случаев на этом этапе можно только проверить, что создано подходящее исключение.  
  
## <a name="example"></a>Пример  
 В этом примере <xref:System.IndexOutOfRangeException> не является наиболее подходящим исключением. Для данного метода больше подходит исключение <xref:System.ArgumentOutOfRangeException>, поскольку ошибка вызвана переданным методу аргументом `index`.  
  
 [!code-cs[csProgGuideExceptions#5](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-handle-an-exception-using-try-catch_1.cs)]  
  
## <a name="comments"></a>Комментарии  
 Код, вызывающий исключение, находится в блоке `try`. Оператор `catch` добавляется сразу после него, чтобы обрабатывать исключение `IndexOutOfRangeException`, если оно происходит. Блок `catch` обрабатывает исключение `IndexOutOfRangeException` и вместо него вызывает более подходящее исключение `ArgumentOutOfRangeException`. Чтобы вызывающий объект получил максимально подробную информацию, рекомендуется указать исходное исключение в качестве значения <xref:System.Exception.InnerException%2A> нового исключения. Поскольку свойство <xref:System.Exception.InnerException%2A> [доступно только для чтения](../../../csharp/language-reference/keywords/readonly.md), его значение необходимо присваивать только в конструкторе нового исключения.  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/index.md)   
 [Обработка исключений](../../../csharp/programming-guide/exceptions/exception-handling.md)
