---
title: "Использование объектов, реализующих IDisposable"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd78c2f99ca5c8ffe3c753e158ceba3e0c458c5b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-objects-that-implement-idisposable"></a>Использование объектов, реализующих IDisposable

Сборщик мусора среды CLR освобождает память, используемую с управляемыми объектами, но реализуют типы, которые используют неуправляемые ресурсы <xref:System.IDisposable> интерфейс, позволяющий память, выделенную для этих неуправляемые ресурсы, которые нужно освободить. По окончании использования объекта, который реализует интерфейс <xref:System.IDisposable>, необходимо вызвать реализацию объекта <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>. Это можно сделать одним из двух способов.  
  
* С помощью оператора `using` (C#) или `Using` (Visual Basic).  
  
* Путем реализации блока `try/finally`.  

## <a name="the-using-statement"></a>Оператор using

Операторы `using` (C#) и `Using` (Visual Basic) упрощают составление кода для создания и очистки объекта. Оператор `using` получает один или больше ресурсов, выполняет заданные операторы, после чего автоматически освобождает объект. Однако оператор `using` полезен только для объектов в области действия метода, в котором они созданы.  
  
В следующем примере для создания и освобождения объекта `using` используется оператор <xref:System.IO.StreamReader?displayProperty=nameWithType>.  
  
[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]  
  
Обратите внимание, что хотя класс <xref:System.IO.StreamReader> реализует интерфейс <xref:System.IDisposable>, который указывает, что используется неуправляемый ресурс, пример явно не вызывает метод <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType>. Когда компилятор C# или Visual Basic встречает оператор `using`, он создает промежуточный язык, эквивалентный следующему коду, который явно содержит блок `try/finally`.  
  
[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]  
  
C# `using` инструкция также позволяет присоединять несколько ресурсов в одной инструкции, что эквивалентно внутри вложенной `using` инструкции. В следующем примере создается два объекта <xref:System.IO.StreamReader> для чтения содержимого двух разных файлов.  
  
[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a>Блок try/finally

Вместо размещения блока `try/finally` в операторе `using` можно реализовать блок `try/finally` напрямую. Это может быть личным стилем программирования или же осуществляться по одной из следующих причин:  
  
* Чтобы включить блок `catch` для обработки исключений, вызванных в блоке `try`. В противном случае исключения, вызываемые оператором `using`, а также создаваемые в блоке `using`, если блок `try/catch` отсутствует, не обрабатываются.  
  
* Чтобы создать экземпляр объекта, реализующего интерфейс <xref:System.IDisposable>, область действия которого не является локальной для блока, в котором он объявлен.  
  
Следующий пример аналогичен предыдущему примеру, за исключением того, что он использует `try/catch/finally` блок для создания экземпляра, использования и удаления <xref:System.IO.StreamReader> объекта и для обработки исключения, вызываемые <xref:System.IO.StreamReader> конструктор и его <xref:System.IO.StreamReader.ReadToEnd%2A> метод. Обратите внимание, что перед вызовом метода `finally` код в блоке <xref:System.IDisposable> проверяет, имеет ли объект, реализующий интерфейс `null`, значение <xref:System.IDisposable.Dispose%2A>. Если этого сделать не удастся, это может привести к исключению <xref:System.NullReferenceException> во время выполнения.  
  
[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]  
  
Можно следовать этому простому шаблону, если выбрать для реализации или если необходимо реализовать `try/finally` блокируются, поскольку язык программирования не поддерживает `using` инструкции, но разрешает прямые вызовы <xref:System.IDisposable.Dispose%2A> метод. 
  
## <a name="see-also"></a>См. также

[Очистка неуправляемых ресурсов](../../../docs/standard/garbage-collection/unmanaged.md)   
[Оператор using (Справочник по C#)](~/docs/csharp/language-reference/keywords/using-statement.md)   
[С помощью оператора (Visual Basic)](~/docs/visual-basic/language-reference/statements/using-statement.md)
