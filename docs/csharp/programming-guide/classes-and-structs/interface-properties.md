---
title: "Свойства интерфейса (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "интерфейсы [C#], свойства"
  - "свойства [C#], в интерфейсах"
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Свойства интерфейса (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Свойства можно объявлять в [интерфейс](../../../csharp/language-reference/keywords/interface.md).  Ниже приведен пример метода доступа индексатора интерфейса:  
  
 [!code-cs[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]  
  
 Метод доступа свойства интерфейса не имеет тела.  Поэтому методы доступа предназначены для того, чтобы указывать, доступно ли свойство для чтения и записи, только для чтения или только для записи.  
  
## Пример  
 В этом примере интерфейс `IEmployee` имеет свойство с доступом записи\/чтения, `Name`, а также свойство только для чтения `Counter`.  Класс `Employee` реализует интерфейс `IEmployee` и использует эти два свойства.  Программа считывает имя нового сотрудника и текущее количество сотрудников и выводит имя сотрудника и его вычисленный номер.  
  
 Можно использовать полное имя свойства, которое ссылается на интерфейс, в котором объявлен член.  Примеры.  
  
 [!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 Это называется [Явная реализация интерфейса](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).  Например, если класс `Employee` реализует два интерфейса `ICitizen` и `IEmployee`, и оба интерфейса имеют свойство `Name`, то обязательна явная реализация члена интерфейса.  То есть, следующее объявление свойства.  
  
 [!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 реализует свойство `Name` для интерфейса `IEmployee`, а следующее объявление:  
  
 [!code-cs[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]  
  
 реализует свойство `Name` в интерфейсе `ICitizen`.  
  
 [!code-cs[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## Пример результатов выполнения  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Использование свойств](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [Сравнение свойств и индексаторов](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)   
 [Индексаторы](../../../csharp/programming-guide/indexers/index.md)   
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)