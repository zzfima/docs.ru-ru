---
title: "sealed (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sealed"
  - "sealed_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "sealed - ключевое слово [C#]"
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
caps.latest.revision: 30
caps.handback.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# sealed (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

При применении к классу модификатор `sealed` запрещает другим классам наследовать от этого класса.  В приведенном примере класс `B` наследует от класса `A`, но ни какие классы не могут наследовать от класса `B`.  
  
```  
class A {}      
sealed class B : A {}  
```  
  
 Модификатор `sealed` можно использовать для метода или свойства, которое переопределяет виртуальный метод или свойство в базовом классе.  Это позволяет классам наследовать от вашего класса, запрещая им при этом переопределять определенные виртуальные методы или свойства.  
  
## Пример  
 В приведенном примере класс `Z` наследует от класса `Y`, но `Z` не может переопределить виртуальную функцию `F`, которая объявлена в классе `X` и запечатана в классе `Y`.  
  
 [!code-cs[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]  
  
 Чтобы предотвратить переопределение производных классов при определении новых методов или свойств, не назначайте их в качестве виртуальных \([virtual](../../../csharp/language-reference/keywords/virtual.md)\).  
  
 Нельзя использовать модификатор [abstract](../../../csharp/language-reference/keywords/abstract.md) с запечатанным классом, поскольку абстрактный класс должен наследоваться классом, реализующим абстрактные методы или свойства.  
  
 При применении `sealed` модификатора к методу или свойству его необходимо всегда использовать с [override](../../../csharp/language-reference/keywords/override.md).  
  
 Поскольку структуры неявно запечатаны, их нельзя наследовать.  
  
 Дополнительные сведения см. в разделе [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Дополнительные примеры см. в разделе [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
## Пример  
 [!code-cs[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]  
  
 Чтобы наследовать от запечатанного класса, можно применить следующую инструкцию в приведенном выше примере:  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 В результате выдается сообщение об ошибке:  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Заметки  
 Определяя, нужно ли запечатывать класс, метод или свойство, имейте в виду следующее:  
  
-   Потенциальные преимущества, которые производные классы могут получить от возможности настраивать ваш класс.  
  
-   Возможные проблемы из\-за того, что производные классы могут корректировать ваши классы, препятствуя их нормальной работе.  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [виртуальные](../../../csharp/language-reference/keywords/virtual.md)