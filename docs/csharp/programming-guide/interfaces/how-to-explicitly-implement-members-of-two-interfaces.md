---
title: "Практическое руководство. Явная реализация членов двух интерфейсов (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "наследование [C#], явная реализация членов интерфейса"
  - "интерфейсы [C#], явная реализация с наследованием"
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Практическое руководство. Явная реализация членов двух интерфейсов (Руководство по программированию на C#)
Явная реализация [интерфейса](../../../csharp/language-reference/keywords/interface.md) позволяет программисту реализовать два интерфейса, имеющие одинаковые имена членов, и осуществить отдельную реализацию для каждого члена интерфейса.  В данном примере отображаются размеры окна как в метрических, так и в британских единицах измерения.  [Класс](../../../csharp/language-reference/keywords/class.md) "Box" реализует два интерфейса: IEnglishDimensions и IMetricDimensions, которые соответствуют различным системам измерения.  Оба интерфейса имеют одинаковые имена членов: "Length" и "Width".  
  
## Пример  
 [!code-cs[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-explicitly-implem_0_1.cs)]  
  
## Отказоустойчивость  
 Если необходимо произвести измерения по умолчанию в британских единицах, реализуйте методы "Length" и "Width" в обычном режиме и явно реализуйте методы "Length" и "Width" из интерфейса IMetricDimensions:  
  
 [!code-cs[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-explicitly-implem_0_2.cs)]  
  
 В этом случае можно получить доступ к британским единицам из экземпляра класса, а к метрическим единицам — из экземпляра интерфейса:  
  
 [!code-cs[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-explicitly-implem_0_3.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)   
 [Практическое руководство. Явная реализация членов интерфейса](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)