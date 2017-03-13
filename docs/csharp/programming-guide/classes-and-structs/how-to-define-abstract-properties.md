---
title: "Практическое руководство. Определение абстрактных свойств (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "абстрактные свойства [C#]"
  - "свойства [C#], абстрактный"
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# Практическое руководство. Определение абстрактных свойств (Руководство по программированию в C#)
В следующем примере показано, как определить [абстрактные](../../../csharp/language-reference/keywords/abstract.md) свойства.  Если объявление абстрактного свойства не предоставляет реализацию методов доступа к свойствам, оно объявляет, что класс поддерживает свойства, но оставляет реализацию метода доступа производному классу.  В следующем примере показано, как реализовать абстрактные свойства, унаследованные от базового класса.  
  
 Этот пример состоит из трех файлов, каждый из которых компилируется отдельно, и на результирующую сборку которого ссылается следующая компиляция.  
  
-   abstractshape.cs: класс `Shape`, содержащий абстрактное свойство `Area`.  
  
-   shapes.cs: вложенные классы класса `Shape`.  
  
-   shapetest.cs: Тестовая программа для отображения областей некоторых производных от `Shape` объектов.  
  
 Для компиляции примера используйте следующую команду:  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 Будет создан исполняемый файл shapetest.exe.  
  
## Пример  
 Этот файл объявляет класс `Shape`, содержащий свойство `Area` типа `double`.  
  
 [!code-cs[csProgGuideInheritance#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_1.cs)]  
  
-   Модификаторы свойства помещаются в самом объявлении свойства.  Примеры.  
  
    ```  
    public abstract double Area  
    ```  
  
-   При объявлении абстрактного свойства \(такого как `Area` в этом примере\) просто указываются имеющиеся методы доступа к свойствам, и их реализация не выполняется.  В этом примере имеется только метод доступа [get](../../../csharp/language-reference/keywords/get.md), поэтому свойство доступно только для чтения.  
  
## Пример  
 В следующем коде показано три вложенных класса `Shape` и переопределение или свойства `Area` для предоставления собственной реализации.  
  
 [!code-cs[csProgGuideInheritance#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_2.cs)]  
  
## Пример  
 В следующем коде показана тестовая программа, создающая ряд производных от `Shape` объектов и печатающая их области.  
  
 [!code-cs[csProgGuideInheritance#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_3.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Практическое руководство. Создание и использование сборок с помощью командной строки](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)