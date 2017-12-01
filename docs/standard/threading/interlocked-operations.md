---
title: "Блокируемые операции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 122058b7e826e27fe6c60c5b07610f7c63e64f78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="interlocked-operations"></a>Блокируемые операции
<xref:System.Threading.Interlocked> Класс предоставляет методы для синхронизации доступа к переменной, которая совместно используется несколькими потоками. Потоки различных процессов могут использовать этот механизм, если переменная находится в общей памяти. Блокируемые операции являются атомарными, т. е. вся операция представляет собой единицу, которая не может быть прервана другой блокируемой операцией с той же переменной. Это имеет значение в операционных системах с преимущественной многопоточностью, когда поток может быть приостановлен после загрузки значения из адреса памяти, но прежде, чем его можно будет изменить или сохранить.  
  
 <xref:System.Threading.Interlocked> Класс предоставляет следующие операции:  
  
-   В .NET Framework версии 2.0 <xref:System.Threading.Interlocked.Add%2A> метод добавляет целочисленное значение для переменной и возвращает новое значение переменной.  
  
-   В .NET Framework версии 2.0 <xref:System.Threading.Interlocked.Read%2A> метод считывает 64-разрядное целое значение в виде атомарной операции. Это пригодится в 32-разрядных операционных системах, где считывание 64-разрядного целого числа обычно не является атомарной операцией.  
  
-   <xref:System.Threading.Interlocked.Increment%2A> И <xref:System.Threading.Interlocked.Decrement%2A> методы увеличивают или уменьшают переменную и возвращают результирующее значение.  
  
-   <xref:System.Threading.Interlocked.Exchange%2A> Метод выполняет атомарный обмен значение в указанной переменной, возвращая текущее значение и заменив его новым значением. На платформе .NET Framework версии 2.0 универсальную перегрузку этого метода можно использовать для обмена значений в переменной любого ссылочного типа. См. раздел <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>.  
  
-   <xref:System.Threading.Interlocked.CompareExchange%2A> Метод также обменивает два значения, но производное от результата сравнения. На платформе .NET Framework версии 2.0 универсальную перегрузку этого метода можно использовать для обмена значений в переменной любого ссылочного типа. См. раздел <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>.  
  
 Современные процессоры методы <xref:System.Threading.Interlocked> часто классов можно реализовать с помощью одной инструкции. В связи с этим они обеспечивают очень высокую производительность синхронизации и могут использоваться для сборки сложных механизмов синхронизации, таких как спин-блокировки.  
  
 Пример, использующий <xref:System.Threading.Monitor> и <xref:System.Threading.Interlocked> классы в сочетании, в разделе [мониторы](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="compareexchange-example"></a>Пример метода CompareExchange  
 <xref:System.Threading.Interlocked.CompareExchange%2A> Метод может использоваться для защиты, которые сложнее, чем простое увеличение и уменьшение вычислений. В следующем примере показан безопасный для потока метод, который добавляется к промежуточному итогу, хранящемуся в виде числа с плавающей запятой. (Для целых чисел, <xref:System.Threading.Interlocked.Add%2A> метод является простым решением.) Полные примеры кода, в разделе перегрузки <xref:System.Threading.Interlocked.CompareExchange%2A> , принимающие аргументы с плавающей запятой одиночной точности и двойной точности (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> и <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a>Нетипизированные перегрузки Exchange и CompareExchange  
 <xref:System.Threading.Interlocked.Exchange%2A> И <xref:System.Threading.Interlocked.CompareExchange%2A> методы имеют перегрузки, принимающие аргументы типа <xref:System.Object>. Первый аргумент в каждой из этих версий — `ref Object` (`ByRef … As Object` в Visual Basic), и безопасность типов требует переменную, передаваемую в следующий аргумент, чтобы быть строго типизированы как <xref:System.Object>; нельзя просто привести первый аргумент к типу <xref:System.Object> При вызове этих методов.  
  
> [!NOTE]
>  В .NET Framework версии 2.0, используйте универсальный перегрузки <xref:System.Threading.Interlocked.Exchange%2A> и <xref:System.Threading.Interlocked.CompareExchange%2A> методы для обмена строго типизированные переменные.  
  
 В следующем примере кода показано свойство типа `ClassA`, которое может быть задано однократно, так как подходит для реализации на платформе .NET Framework версии 1.0 или 1.1.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
