---
title: "Interlocked Operations | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Interlocked class, about Interlocked class"
  - "threading [.NET Framework], Interlocked class"
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Interlocked Operations
Класс <xref:System.Threading.Interlocked> содержит методы для синхронизации доступа к переменной, которая совместно используется несколькими потоками.  Если переменная находится в общей памяти, этот механизм может использоваться потоками различных процессов.  Блокируемые операции являются атомарными. Это значит, что вся операция является неделимой и не может прерываться другой блокируемой операцией с той же переменной.  Это важно в операционных системах, использующих многопоточность с вытеснением, где поток может быть приостановлен после того, как он загрузит значение из адреса памяти, но до того, как он получит возможность изменить это значение и сохранить в памяти.  
  
 Класс <xref:System.Threading.Interlocked> выполняет следующие операции.  
  
-   В платформе .NET Framework версии 2.0 метод <xref:System.Threading.Interlocked.Add%2A> добавляет к переменной целочисленное значение и возвращает новое значение переменной.  
  
-   В платформе .NET Framework версии 2.0, метод <xref:System.Threading.Interlocked.Read%2A> считывает 64\-разрядное целочисленное значение в ходе атомарной операции.  Это полезно в 32\-разрядных операционных системах, где считывание 64\-разрядного целого числа обычно не является атомарной операцией.  
  
-   Методы <xref:System.Threading.Interlocked.Increment%2A> и <xref:System.Threading.Interlocked.Decrement%2A> увеличивают или уменьшают переменную и возвращают результирующее значение.  
  
-   Метод <xref:System.Threading.Interlocked.Exchange%2A> выполняет атомарный обмен значений для указанной переменной, возвращая текущее значение и заменяя его новым значением.  Универсальная перегружаемая версия этого метода в платформе .NET Framework версии 2.0 может использоваться для обмена значений в переменной любого ссылочного типа.  См. раздел <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>.  
  
-   Метод <xref:System.Threading.Interlocked.CompareExchange%2A> также обменивает два значения, но делает это в зависимости от результата сравнения.  Универсальная перегружаемая версия этого метода в платформе .NET Framework версии 2.0 может использоваться для обмена значений в переменной любого ссылочного типа.  См. раздел <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>.  
  
 Современные процессоры часто позволяют реализовать методы класса <xref:System.Threading.Interlocked> одной инструкцией.  Поэтому они обеспечивают очень высокую производительность синхронизации и позволяют построить механизмы синхронизации более высокого уровня, такие как спин\-блокировка.  
  
 Пример, использующий сочетание классов <xref:System.Threading.Monitor> и <xref:System.Threading.Interlocked>, см. в разделе [Мониторы](../Topic/Monitors.md).  
  
## Пример CompareExchange  
 Метод <xref:System.Threading.Interlocked.CompareExchange%2A> служит для защиты более сложных вычислений, чем простое увеличение и уменьшение значений.  В следующем примере показан потокобезопасный метод, который добавляет значение к промежуточной сумме, хранящейся в виде числа с плавающей запятой. \(Для целочисленных значений более простым решением будет метод <xref:System.Threading.Interlocked.Add%2A>.\) Полные примеры кода см. в описании перегруженных версий метода <xref:System.Threading.Interlocked.CompareExchange%2A>, которые принимают аргументы с плавающей запятой одинарной и двойной точности \(<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> и <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>\).  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## Нетипизированные перегруженные версии методов Exchange и CompareExchange  
 Методы <xref:System.Threading.Interlocked.Exchange%2A> и <xref:System.Threading.Interlocked.CompareExchange%2A> имеют перегруженные версии, принимающие аргументы типа <xref:System.Object>.  Первый аргумент в каждой из этих версий имеет тип `ref Object` \(`ByRef … As Object` в Visual Basic\), и для безопасности типов необходима строгая типизация переменной, передаваемой этому аргументу, по типу <xref:System.Object>. При вызове этих методов нельзя просто привести первый аргумент к типу <xref:System.Object>.  
  
> [!NOTE]
>  В платформе .NET Framework версии 2.0 для обмена строго типизированными переменными используются универсальные перегружаемые версии методов <xref:System.Threading.Interlocked.Exchange%2A> и <xref:System.Threading.Interlocked.CompareExchange%2A>.  
  
 В следующем примере кода показано свойство типа `ClassA`, которое может задаваться только один раз, и его реализация в платформе .NET Framework версии 1.0 или 1.1.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## См. также  
 <xref:System.Threading.Interlocked>   
 <xref:System.Threading.Monitor>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)