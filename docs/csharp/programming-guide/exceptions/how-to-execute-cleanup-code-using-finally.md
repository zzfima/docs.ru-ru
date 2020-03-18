---
title: Руководство по программированию на C#. Выполнение кода очистки с использованием блока finally
ms.date: 07/20/2015
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: d1ba761e64053d656ad4cd004133fc455a57c6f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705279"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a>Руководство по программированию на C#. Выполнение кода очистки с использованием блока finally
Оператор `finally` позволяет гарантировать, что необходимая очистка объектов, как правило, объектов, занимающих внешние ресурсы, возникает немедленно, даже при создании исключения. Примером подобной очистки является вызов <xref:System.IO.Stream.Close%2A> для <xref:System.IO.FileStream> сразу после использования вместо ожидания сборки мусора, выполняемой для объекта средой CLR, следующим образом:  
  
 [!code-csharp[csProgGuideExceptions#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#16)]  
  
## <a name="example"></a>Пример  
 Чтобы преобразовать предыдущий код в оператор `try-catch-finally`, код очистки отделяется от рабочего кода следующим образом:  
  
 [!code-csharp[csProgGuideExceptions#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#17)]  
  
 Так как исключение может возникнуть в любой момент в блоке `try` до вызова `OpenWrite()`, или может произойти сбой самого вызова `OpenWrite()`, мы не можем гарантировать, что файл будет открыт при попытке закрыть его. Блок `finally` добавляет проверку того, что объект <xref:System.IO.FileStream> имеет отличное от `null` значение, прежде чем будет вызван метод <xref:System.IO.Stream.Close%2A>. Без проверки `null` блок `finally` может создавать собственное исключение <xref:System.NullReferenceException>, однако создания исключений в блоках `finally` следует по возможности избегать.  
  
 Подключение к базе данных — еще один подходящий кандидат для заключения в блок `finally`. Так как количество разрешенных подключений к серверу базы данных иногда ограничено, закрывать подключения к базе данных рекомендуется как можно быстрее. Если перед закрытием подключения возникает исключение, это еще один случай, когда использование блока `finally` предпочтительнее, чем ожидание сборки мусора.  
  
## <a name="see-also"></a>См. также раздел

- [Руководство по программированию на C#](../index.md)
- [Исключения и обработка исключений](./index.md)
- [Обработка исключений](./exception-handling.md)
- [Оператор using](../../language-reference/keywords/using-statement.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
