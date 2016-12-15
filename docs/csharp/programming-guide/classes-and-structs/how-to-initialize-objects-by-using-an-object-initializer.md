---
title: "Практическое руководство. Инициализация объектов с помощью инициализатора объектов (Руководство по программированию на C#). | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "инициализаторы объектов [C#], использование"
  - "объекты [C#], инициализация"
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Инициализация объектов с помощью инициализатора объектов (Руководство по программированию на C#).
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Можно использовать инициализаторы объектов для декларативной инициализации объектов типов без явного вызова конструктора типа.  
  
 В следующем примере показано, как использовать инициализаторы объектов с именованными объектами.  Компилятор рассматривает инициализаторы объекта сначала получить доступ к конструктору экземпляра по умолчанию, а затем обработать инициализации членов.  Таким образом, при объявлении конструктора по умолчанию в классе как `private`, обработка инициализаторов объектов, требующих открытый доступ, приведет к ошибке.  
  
 Необходимо использовать инициализатор объекта при указании анонимный тип.  Дополнительные сведения см. в разделе [Практическое руководство. Возвращение поднаборов свойств элементов в запросе](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## Пример  
 В следующем примере показано, как инициализировать новый тип `StudentName` с помощью инициализаторов объектов.  
  
 [!code-cs[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## Пример  
 В следующем примере показано, как инициализировать коллекцию типов `StudentName` с помощью инициализатора коллекции.  Обратите внимание, что инициализаторе коллекции представляет собой ряд инициализаторов объектов, перечисленных через запятую.  
  
 [!code-cs[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## Компиляция кода  
 Для выполнения этого кода скопируйте класс в проект консольного приложения на языке Visual C\#, которое было создано в среде разработки [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].  Дополнительные сведения см. в разделе [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)