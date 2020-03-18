---
title: Использование объектов, реализующих IDisposable
ms.date: 04/07/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
ms.openlocfilehash: c5232aa89064c514e71f3a18bc754159e9c9b15b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160289"
---
# <a name="using-objects-that-implement-idisposable"></a>Использование объектов, реализующих IDisposable

Сборщик мусора среды CLR освобождает память, используемую управляемыми объектами, но типы, которые используют неуправляемые ресурсы, реализуют интерфейс <xref:System.IDisposable>, который позволяет освободить память, выделенную таким неуправляемым ресурсам. По окончании использования объекта, который реализует интерфейс <xref:System.IDisposable>, необходимо вызвать реализацию объекта <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>. Это можно сделать одним из двух способов.  
  
- С помощью оператора `using` (C#) или `Using` (Visual Basic).  
  
- Путем реализации блока `try/finally`.  

## <a name="the-using-statement"></a>Оператор using

Операторы `using` (C#) и `Using` (Visual Basic) упрощают составление кода для создания и очистки объекта. Оператор `using` получает один или больше ресурсов, выполняет заданные операторы, после чего автоматически освобождает объект. Однако оператор `using` полезен только для объектов в области действия метода, в котором они созданы.  
  
В следующем примере для создания и освобождения объекта `using` используется оператор <xref:System.IO.StreamReader?displayProperty=nameWithType>.  
  
[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]  
  
Обратите внимание, что хотя класс <xref:System.IO.StreamReader> реализует интерфейс <xref:System.IDisposable>, который указывает, что используется неуправляемый ресурс, пример явно не вызывает метод <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType>. Когда компилятор C# или Visual Basic встречает оператор `using`, он создает промежуточный язык, эквивалентный следующему коду, который явно содержит блок `try/finally`.  
  
[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]  
  
Оператор `using` в C# позволяет присоединять несколько ресурсов в одном операторе, что эквивалентно использованию вложенных инструкций `using`. В следующем примере создается два объекта <xref:System.IO.StreamReader> для чтения содержимого двух разных файлов.  
  
[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a>Блок try/finally

Вместо размещения блока `try/finally` в операторе `using` можно реализовать блок `try/finally` напрямую. Это может быть личным стилем программирования или же осуществляться по одной из следующих причин:  
  
- Чтобы включить блок `catch` для обработки исключений, вызванных в блоке `try`. В противном случае исключения, вызываемые оператором `using`, а также создаваемые в блоке `using`, если блок `try/catch` отсутствует, не обрабатываются.  
  
- Чтобы создать экземпляр объекта, реализующего интерфейс <xref:System.IDisposable>, область действия которого не является локальной для блока, в котором он объявлен.  
  
Следующий пример похож на предыдущий с тем отличием, что в нем используется блок `try/catch/finally`для создания, использования и удаления экземпляра объекта <xref:System.IO.StreamReader>, а также для обработки исключений, создаваемых конструктором <xref:System.IO.StreamReader> и его методом <xref:System.IO.StreamReader.ReadToEnd%2A>. Обратите внимание, что перед вызовом метода `finally` код в блоке <xref:System.IDisposable> проверяет, имеет ли объект, реализующий интерфейс `null`, значение <xref:System.IDisposable.Dispose%2A>. Если этого сделать не удастся, это может привести к исключению <xref:System.NullReferenceException> во время выполнения.  
  
[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]  
  
Вы можете применить этот базовый шаблон, если есть желание или необходимость реализовать блок `try/finally` на языке программирования, который не поддерживает оператор `using`, но допускает прямые вызовы метода <xref:System.IDisposable.Dispose%2A>.
  
## <a name="see-also"></a>См. также раздел

- [Очистка неуправляемых ресурсов](../../../docs/standard/garbage-collection/unmanaged.md)
- [Оператор using (Справочник по C#)](../../csharp/language-reference/keywords/using-statement.md)
- [Оператор Using (Visual Basic)](../../visual-basic/language-reference/statements/using-statement.md)
