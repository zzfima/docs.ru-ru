---
title: Блокируемые операции
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38532228f7a5d07bb1b9fcf7e90d2be53a28b04c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="interlocked-operations"></a>Блокируемые операции
Класс <xref:System.Threading.Interlocked> предоставляет методы для синхронизации доступа к переменной, которую совместно используют несколько потоков. Потоки различных процессов могут использовать этот механизм, если переменная находится в общей памяти. Блокируемые операции являются атомарными, т. е. вся операция представляет собой единицу, которая не может быть прервана другой блокируемой операцией с той же переменной. Это имеет значение в операционных системах с преимущественной многопоточностью, когда поток может быть приостановлен после загрузки значения из адреса памяти, но прежде, чем его можно будет изменить или сохранить.  
  
 Класс <xref:System.Threading.Interlocked> предоставляет следующие операции:  
  
-   На платформе .NET Framework версии 2.0 метод <xref:System.Threading.Interlocked.Add%2A> добавляет к переменной целочисленное значение и возвращает новое значение переменной.  
  
-   На платформе .NET Framework версии 2.0 метод <xref:System.Threading.Interlocked.Read%2A> считывает 64-разрядное целочисленное значение в атомарной операции. Это пригодится в 32-разрядных операционных системах, где считывание 64-разрядного целого числа обычно не является атомарной операцией.  
  
-   Методы <xref:System.Threading.Interlocked.Increment%2A> и <xref:System.Threading.Interlocked.Decrement%2A> приращивают или уменьшают значение переменной и возвращают результат.  
  
-   Метод <xref:System.Threading.Interlocked.Exchange%2A> выполняет атомарный обмен значения в указанной переменной, то есть возвращает это значение и заменяет его новым. На платформе .NET Framework версии 2.0 универсальную перегрузку этого метода можно использовать для обмена значений в переменной любого ссылочного типа. См. раздел <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>.  
  
-   Метод <xref:System.Threading.Interlocked.CompareExchange%2A> также обменивает два значения, но только при правильном результате сравнения. На платформе .NET Framework версии 2.0 универсальную перегрузку этого метода можно использовать для обмена значений в переменной любого ссылочного типа. См. раздел <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>.  
  
 Для современных процессоров методы класса <xref:System.Threading.Interlocked> часто можно реализовать в одной инструкции. В связи с этим они обеспечивают очень высокую производительность синхронизации и могут использоваться для сборки сложных механизмов синхронизации, таких как спин-блокировки.  
  
 Пример, в котором используется сочетание классов <xref:System.Threading.Monitor> и <xref:System.Threading.Interlocked>, можно найти в описании класса [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="compareexchange-example"></a>Пример метода CompareExchange  
 Метод <xref:System.Threading.Interlocked.CompareExchange%2A> может использоваться для защиты более сложных вычислений, чем простое приращение и уменьшение. В следующем примере показан безопасный для потока метод, который добавляется к промежуточному итогу, хранящемуся в виде числа с плавающей запятой. (Для целых чисел проще использовать метод <xref:System.Threading.Interlocked.Add%2A>.) Полные примеры кода вы найдете в описании перегрузок <xref:System.Threading.Interlocked.CompareExchange%2A>, которые принимают аргументы с плавающей запятой одиночной и двойной точности (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> и <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a>Нетипизированные перегрузки Exchange и CompareExchange  
 Методы <xref:System.Threading.Interlocked.Exchange%2A> и <xref:System.Threading.Interlocked.CompareExchange%2A> имеют перегрузки, принимающие аргументы типа <xref:System.Object>. Первым аргументом в каждой такой перегрузке является `ref Object` (`ByRef … As Object` в Visual Basic), а для безопасности типов переменная, которая передается в этот аргумент, должна быть строго типизирована как <xref:System.Object>. При вызове этих методов недостаточно просто привести первый аргумент к типу <xref:System.Object>.  
  
> [!NOTE]
>  На платформе .NET Framework версии 2.0 используйте универсальные перегрузки методов <xref:System.Threading.Interlocked.Exchange%2A> и <xref:System.Threading.Interlocked.CompareExchange%2A> для обмена значений строго типизированных переменных.  
  
 В следующем примере кода показано свойство типа `ClassA`, которое может быть задано однократно, так как подходит для реализации на платформе .NET Framework версии 1.0 или 1.1.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
