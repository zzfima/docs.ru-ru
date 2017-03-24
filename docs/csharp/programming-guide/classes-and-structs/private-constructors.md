---
title: "Закрытые конструкторы (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, закрытые конструкторы"
  - "закрытые конструкторы [C#]"
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Закрытые конструкторы (Руководство по программированию на C#)
Закрытый конструктор — это особый конструктор экземпляров.  Обычно он используется в классах, содержащих только статические элементы.  Если в классе один или несколько закрытых конструкторов и ни одного открытого конструктора, то прочие классы \(за исключением вложенных классов\) не смогут создавать экземпляры этого класса.  Примеры.  
  
 [!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]  
  
 Объявление пустого конструктора запрещает автоматическое создание конструктора по умолчанию.  Обратите внимание, что если не использовать с конструктором модификатор доступа, то по умолчанию он все равно будет закрытым.  Однако обычно используется модификатор [private](../../../csharp/language-reference/keywords/private.md), чтобы ясно обозначить невозможность создания экземпляров данного класса.  
  
 Закрытые конструкторы используются, чтобы не допустить создание экземпляров класса при отсутствии полей или методов экземпляра, например для класса <xref:System.Math>, или когда осуществляется вызов метода для получения экземпляра класса.  Если все методы в классе являются статическими, имеет смысл сделать статическим весь класс.  Дополнительные сведения см. в разделе [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## Пример  
 Ниже приведен пример класса с закрытым конструктором.  
  
 [!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]  
  
 Обратите внимание, что если снять комментарий со следующего оператора в примере, возникнет ошибка, поскольку конструктор недоступен из\-за уровня защиты:  
  
 [!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Деструкторы](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [закрытый](../../../csharp/language-reference/keywords/private.md)   
 [public](../../../csharp/language-reference/keywords/public.md)