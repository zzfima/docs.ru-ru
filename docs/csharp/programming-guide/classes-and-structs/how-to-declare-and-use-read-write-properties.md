---
title: "Практическое руководство. Объявление и использование свойств чтения и записи (руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "метод доступа get [C#], объявление свойств"
  - "set - метод доступа [C#]"
  - "свойства [C#], объявление"
  - "свойства чтения/записи [C#]"
  - "методы доступа [C#], объявление свойств с помощью"
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Практическое руководство. Объявление и использование свойств чтения и записи (руководство по программированию на C#)
Свойства обеспечивают удобную работу с открытыми членами данных без риска, с которым связан незащищенный, неконтролируемый и непроверяемый доступ к данным объекта.  Это достигается с помощью *методов доступа*: особых методов, которые назначают и извлекают значения из базового члена данных.  Метод доступа [set](../../../csharp/language-reference/keywords/set.md) обеспечивает назначение членов данных, а метод [get](../../../csharp/language-reference/keywords/get.md) извлекает значения членов данных.  
  
 В этом примере показан простой класс `Person`, имеющий два свойства: `Name`\(string\) и `Age` \(int\).  Оба свойства предоставляют методы доступа `get` и `set`, поэтому они считаются свойствами чтения и записи.  
  
## Пример  
 [!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-declare-and-use-r_1.cs)]  
  
## Отказоустойчивость  
 В предыдущем примере свойства `Name` и `Age` являются [открытыми](../../../csharp/language-reference/keywords/public.md) и содержат методы доступа `get` и `set`.  При этом любой объект может выполнять чтение и запись данных свойств.  Однако иногда рекомендуется исключить один из методов доступа.  Если, например, будет опущен метод доступа `set`, средство станет доступным только для чтения.  
  
 [!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-declare-and-use-r_2.cs)]  
  
 Можно также сделать один метод доступа открытым, а другой — закрытым или защищенным.  Дополнительные сведения см. в разделе [Простота использования асимметричных методов доступа\)](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
 Объявленные свойства могут использоваться в качестве полей класса.  Это приводит к более естественному синтаксису, где выполняется получение и установка значения свойства, как в следующих операторах.  
  
 [!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-declare-and-use-r_3.cs)]  
  
 Обратите внимание, что в свойстве метода `set` доступна особая переменная `value`.  Эта переменная содержит значение, заданное пользователем, например:  
  
 [!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-declare-and-use-r_4.cs)]  
  
 Обратите внимание на чистый синтаксис для увеличения значения свойства `Age` объекта `Person`.  
  
 [!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-declare-and-use-r_5.cs)]  
  
 Если для моделирования свойств использовались отдельные методы `set` и `get`, эквивалентный код может выглядеть следующим образом.  
  
```  
person.SetAge(person.GetAge() + 1);   
```  
  
 В этом примере метод `ToString` переопределен.  
  
 [!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-declare-and-use-r_6.cs)]  
  
 Обратите внимание, что `ToString` не используется явно в программе.  Он вызывается по умолчанию вызовами `WriteLine`.  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)