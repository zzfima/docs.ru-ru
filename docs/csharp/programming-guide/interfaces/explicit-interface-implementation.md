---
title: "Явная реализация интерфейса (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "явные интерфейсы [C#]"
  - "интерфейсы [C#], явные"
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Явная реализация интерфейса (Руководство по программированию в C#)
Если [класс](../../../csharp/language-reference/keywords/class.md) реализует два интерфейса, содержащих член с одинаковой сигнатурой, то при реализации этого члена в классе оба интерфейса будут использовать этот член для своей реализации.  В следующем примере все вызовы `Paint` вызывают один метод.  
  
 [!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/explicit-interface-imple_1.cs)]  
  
 Однако, если члены двух [интерфейсов](../../../csharp/language-reference/keywords/interface.md) не выполняют одинаковую функцию, это может привести к неверной реализации одного или обоих интерфейсов.  Возможна явная реализация члена интерфейса — путем создания члена класса, который вызывается только через интерфейс и имеет отношение только к этому интерфейсу.  Это достигается путем включения в имя члена класса имени интерфейса с точкой.  Например:  
  
 [!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/explicit-interface-imple_2.cs)]  
  
 Член класса `IControl.Paint` доступен только через интерфейс `IControl`, а член `ISurface.Paint` — только через интерфейс `ISurface`.  Каждая реализация метода является независимой и недоступна в классе напрямую.  Например:  
  
 [!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/explicit-interface-imple_3.cs)]  
  
 Явная реализация также используется для разрешения случаев, когда каждый из двух интерфейсов объявляет разные члены с одинаковым именем, например свойство и метод.  
  
 [!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/explicit-interface-imple_4.cs)]  
  
 Для реализации обоих интерфейсов классу необходимо использовать явную реализацию либо для свойства P, либо для метода P, либо для обоих членов, чтобы избежать ошибки компилятора.  Например:  
  
 [!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/explicit-interface-imple_5.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)   
 [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md)