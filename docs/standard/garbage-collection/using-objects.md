---
title: "Using Objects That Implement IDisposable | Microsoft Docs"
ms.custom: ""
ms.date: "04/07/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Dispose method"
  - "try/finally block"
  - "garbage collection, encapsulating resources"
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Using Objects That Implement IDisposable
Сборщик мусора среды CLR освобождает память, используемую неуправляемыми объектами, но типы, которые используют неуправляемые ресурсы, реализуют интерфейс <xref:System.IDisposable>, который позволяет освободить неуправляемую память.  По окончании использования объекта, который реализует интерфейс <xref:System.IDisposable>, необходимо вызвать реализацию объекта <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>.  Это можно сделать одним из двух способов.  
  
-   С помощью оператора **using** \(C\#\) или `Using` \(Visual Basic\).  
  
-   Путем реализации блока `try`\/`finally`.  
  
## Оператор using  
 Операторы **using** \(C\#\) и `Using` \(Visual Basic\) упрощают составление кода для создания и очистки объекта.  Оператор **using** получает один или больше ресурсов, выполняет заданные операторы, после чего автоматически освобождает объект.  Однако оператор **using** полезен только для объектов в области действия метода, в котором они созданы.  
  
 В следующем примере для создания и освобождения объекта <xref:System.IO.StreamReader?displayProperty=fullName> используется оператор `using`.  
  
 [!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
 [!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]  
  
 Обратите внимание, что хотя класс <xref:System.IO.StreamReader> реализует интерфейс <xref:System.IDisposable>, который указывает, что используется неуправляемый ресурс, пример явно не вызывает метод <xref:System.IO.StreamReader.Dispose%2A?displayProperty=fullName>.  Когда компилятор C\# или Visual Basic встречает оператор `using`, он создает промежуточный язык, эквивалентный следующему коду, который явно содержит блок `try`\/`finally`.  
  
 [!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
 [!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]  
  
 Оператор **using** в C\# позволяет присоединять несколько ресурсов в одном операторе, что эквивалентно использованию вложенных инструкций **using**.  В следующем примере создается два объекта <xref:System.IO.StreamReader> для чтения содержимого двух разных файлов.  
  
 [!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]  
  
## Блок try\/finally  
 Вместо размещения блока `try`\/`finally` в операторе `using` можно реализовать блок `try`\/`finally` напрямую.  Это может быть личным стилем программирования или же осуществляться по одной из следующих причин:  
  
-   Чтобы включить блок `catch` для обработки исключений, вызванных в блоке `try`.  В противном случае исключения, вызываемые оператором `using`, а также создаваемые в блоке `using`, если блок `try`\/`catch` отсутствует, не обрабатываются.  
  
-   Чтобы создать экземпляр объекта, реализующего интерфейс <xref:System.IDisposable>, область действия которого не является локальной для блока, в котором он объявлен.  
  
 Следующий пример похож на предыдущий с тем отличием, что в нем используется блок `try`\/`catch`\/`finally` для создания экземпляра, использования и удаления объекта <xref:System.IO.StreamReader>, а также для обработки исключений, вызываемых конструктором <xref:System.IO.StreamReader> и его методом <xref:System.IO.StreamReader.ReadToEnd%2A>.  Обратите внимание, что перед вызовом метода <xref:System.IDisposable.Dispose%2A> код в блоке `finally` проверяет, имеет ли объект, реализующий интерфейс <xref:System.IDisposable>, значение `null`.  Если этого сделать не удастся, это может привести к исключению <xref:System.NullReferenceException> во время выполнения.  
  
 [!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
 [!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]  
  
 Можно следовать этому простому шаблону, если необходимо реализовать блок `try`\/`finally`, поскольку язык программирования не поддерживает оператор `using`, но разрешает прямые вызовы метода <xref:System.IDisposable.Dispose%2A>.  
  
 Если язык не поддерживает прямые вызовы метода <xref:System.IDisposable.Dispose%2A> \(например, C\+\+\), обычно можно использовать синтаксис деструктора.  
  
## См. также  
 [Cleaning Up Unmanaged Resources](../../../docs/standard/garbage-collection/unmanaged.md)   
 [Оператор using](../Topic/using%20Statement%20\(C%23%20Reference\).md)   
 [Оператор Using](../Topic/Using%20Statement%20\(Visual%20Basic\).md)