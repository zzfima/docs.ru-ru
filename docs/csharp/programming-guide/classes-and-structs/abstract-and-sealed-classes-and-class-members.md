---
title: "Абстрактные и запечатанные классы и члены классов (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "абстрактные классы [C#]"
  - "запечатанные классы [C#]"
  - "язык C#, абстрактные классы"
  - "язык C#, запечатанные"
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Абстрактные и запечатанные классы и члены классов (Руководство по программированию на C#)
Ключевое слово [abstract](../../../csharp/language-reference/keywords/abstract.md) позволяет создавать классы и члены [классов](../../../csharp/language-reference/keywords/class.md), которые являются неполными и должны быть реализованы в производном классе.  
  
 Ключевое слово [sealed](../../../csharp/language-reference/keywords/sealed.md) позволяет предотвратить наследование класса или определенных членов класса, помеченных ранее как [virtual](../../../csharp/language-reference/keywords/virtual.md).  
  
## Абстрактные классы и члены классов  
 Классы могут быть объявлены абстрактными путем помещения ключевого слова `abstract` перед определением класса.  Например:  
  
 [!code-cs[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]  
  
 Создавать экземпляры абстрактного класса нельзя.  Назначение абстрактного класса заключается в предоставлении общего определения для базового класса, которое могут совместно использовать несколько производных классов.  Например, в библиотеке классов может быть определен абстрактный класс, используемый в качестве параметра для многих из ее функций, поэтому программисты, использующие эту библиотеку, должны задать свою реализацию этого класса, создав производный класс.  
  
 Абстрактные классы могут определять абстрактные методы.  Для этого перед типом возвращаемого значения метода необходимо поместить ключевое слово `abstract`.  Например:  
  
 [!code-cs[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]  
  
 Абстрактные методы не имеют реализации, поэтому определение такого метода заканчивается точкой с запятой вместо обычного блока метода.  Классы, производные от абстрактного класса, должны реализовывать все абстрактные методы.  Если абстрактный класс наследует виртуальный метод из базового класса, абстрактный класс может переопределить виртуальный метод с помощью абстрактного метода.  Например:  
  
 [!code-cs[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]  
  
 Если метод `virtual` объявляется как `abstract`, он все равно считается виртуальным по отношению к любому классу, наследующему от абстрактного класса.  Класс, наследующий абстрактный метод, не может обращаться к исходной реализации метода — см. предыдущий пример, `DoWork` в классе F не может вызывать `DoWork` в классе D.  Таким образом абстрактный класс может "принуждать" производные классы предоставлять новые реализации для виртуальных методов.  
  
## Запечатанные классы и члены классов  
 Классы могут быть объявлены как [запечатанные](../../../csharp/language-reference/keywords/sealed.md) путем помещения ключевого слова `sealed` перед определением класса.  Например:  
  
 [!code-cs[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]  
  
 Запечатанный класс не может использоваться в качестве базового класса.  Поэтому он также не может быть абстрактным классом.  Запечатанные классы предотвращают наследование.  Поскольку их нельзя использовать в качестве базовых классов, определенная оптимизация во время выполнения позволяет несколько ускорить вызов членов запечатанных классов.  
  
 Метод, индексатор, свойство или событие для производного класса, переопределяющего виртуальный член базового класса, может объявлять этот член как запечатанный.  Это делает бесполезным виртуальный аспект члена для каждого последующего производного класса.  Для этого в объявлении члена класса необходимо перед ключевым словом [override](../../../csharp/language-reference/keywords/override.md) поместить ключевое слово `sealed`.  Например:  
  
 [!code-cs[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Поля](../../../csharp/programming-guide/classes-and-structs/fields.md)   
 [Практическое руководство. Определение абстрактных свойств](../../../csharp/programming-guide/classes-and-structs/how-to-define-abstract-properties.md)