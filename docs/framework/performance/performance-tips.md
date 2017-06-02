---
title: "Советы по производительности .NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "C# - язык, производительность"
  - "производительность [C#]"
  - "производительность [Visual Basic]"
  - "Visual Basic, производительность"
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
caps.latest.revision: 36
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
caps.handback.revision: 36
---
# Советы по производительности .NET
Термин *производительность* обычно относится к скорости выполнения программы.  Иногда можно увеличить скорость выполнения, следуя определенным основным правилам в исходном коде.  В некоторых программах важно внимательно изучить код и использовать профилировщики, чтобы гарантировать, что он выполняется максимально быстро.  В других программах нет необходимости выполнять такую оптимизацию, поскольку код выполняется приемлемо быстро при его написании.  В этой статье список общих областей, в которых может пострадать производительность, а также советы по совершенствованию, ссылки на дополнительные разделы о производительности.  Дополнительные сведения о планировании и измерении производительности см. в разделе [Performance](../../../docs/framework/performance/index.md).  
  
## Упаковка–преобразование и распаковка–преобразование  
 Лучше всего избегать использования типов значений в случаях, когда они должны быть упакованы много раз, например в не универсальных классах коллекций, например, <xref:System.Collections.ArrayList?displayProperty=fullName>.  Упаковки\-преобразования типов значений можно избежать с помощью универсальных коллекций, например, <xref:System.Collections.Generic.List%601?displayProperty=fullName>.  Упаковка и распаковка являются процессами, требующими с точки зрения вычислений больших затрат.  При упаковке типа значения должен быть создан совершенно новый объект.  Это действие занимает на 20 минут больше времени, чем назначение простой ссылки.  При распаковке процесс приведения может длиться в четыре раза дольше назначения.  Дополнительные сведения см. в разделе [Упаковка–преобразование и распаковка–преобразование](../Topic/Boxing%20and%20Unboxing%20\(C%23%20Programming%20Guide\).md).  
  
## Строки  
 При объединении большого количества строковых переменных, например в непрерывном цикле, используйте <xref:System.Text.StringBuilder?displayProperty=fullName> вместо [оператора \+](../Topic/+%20Operator%20\(C%23%20Reference\).md) в C\# или [операторов объединения](../Topic/Concatenation%20Operators%20\(Visual%20Basic\).md) в Visual Basic.  Дополнительные сведения см. в разделах [Практическое руководство. Сцепка нескольких строк](../Topic/How%20to:%20Concatenate%20Multiple%20Strings%20\(C%23%20Programming%20Guide\).md) и [Операторы объединения в Visual Basic](../Topic/Concatenation%20Operators%20in%20Visual%20Basic.md).  
  
## Деструкторы  
 Пустые деструкторы использовать не следует.  Если класс содержит деструктор, в очереди финализации будет создана запись.  При вызове деструктора вызывается сборщик мусора, выполняющий обработку очереди.  Если деструктор пустой, происходит снижение производительности.  Дополнительные сведения см. в разделах [Деструкторы](../Topic/Destructors%20\(C%23%20Programming%20Guide\).md) и [Время существования: создание и уничтожение объектов](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md).  
  
## Другие ресурсы  
  
-   [Writing Faster Managed Code: Know What Things Cost](http://go.microsoft.com/fwlink/?LinkId=99294)  
  
-   [Writing High\-Performance Managed Applications: A Primer](http://go.microsoft.com/fwlink/?LinkId=99295)  
  
-   [Garbage Collector Basics and Performance Hints](http://go.microsoft.com/fwlink/?LinkId=99296)  
  
-   [Советы и подсказки производительности в приложениях .NET](http://go.microsoft.com/fwlink/?LinkId=99297)  
  
-   [Inside Diagnostic Tools for .NET](http://go.microsoft.com/fwlink/?LinkId=112407)  
  
-   [Советы по повышению производительности Rico Mariani](http://go.microsoft.com/fwlink/?LinkId=115679)  
  
## См. также  
 [Performance](../../../docs/framework/performance/index.md)   
 [Основные понятия программирования](../Topic/Programming%20Concepts.md)   
 [Руководство по программированию на Visual Basic](../Topic/Visual%20Basic%20Programming%20Guide.md)   
 [Руководство по программированию на C\#](../Topic/C%23%20Programming%20Guide.md)