---
title: Индексаторы в интерфейсах (Руководство по программированию в C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 478920b5c1dea489db48caa48c045c4bd3da66ec
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="indexers-in-interfaces-c-programming-guide"></a>Индексаторы в интерфейсах (Руководство по программированию в C#)
Индексаторы можно объявлять для [интерфейса](../../../csharp/language-reference/keywords/interface.md). Методы доступа индексаторов интерфейса отличаются от методов доступа индексаторов [класса](../../../csharp/language-reference/keywords/class.md) следующим образом:  
  
-   Методы доступа интерфейса не используют модификаторы.  
  
-   Метод доступа интерфейса не имеет тела.  
  
 Таким образом, методы доступа нужны, чтобы указать, доступен ли индексатор для чтения и записи, только для чтения или только для записи.  
  
 Ниже показан пример метода доступа индексатора для интерфейса:  
  
 [!code-csharp[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]  
  
 Сигнатура индексатора должна отличаться от сигнатур любых других индексаторов, объявленных в том же интерфейсе.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует реализацию индексаторов интерфейса.  
  
 [!code-csharp[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]  
  
 В приведенном выше примере можно использовать явную реализацию члена интерфейса с помощью полного имени члена интерфейса. Пример:  
  
```  
public string ISomeInterface.this[int index]   
{   
}   
```  
  
 Тем не менее полное имя требуется только в целях устранения неоднозначности, если класс реализует более одного интерфейса с одинаковой сигнатурой индексатора. Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых имеют одинаковую сигнатуру индексатора, требуется явная реализация члена интерфейса. Это значит, что потребуется следующее объявление индексатора:  
  
```  
public string IEmployee.this[int index]   
{   
}   
```  
  
 реализует индексатор в интерфейсе `IEmployee`, тогда как следующее объявление:  
  
```  
public string ICitizen.this[int index]
{   
}   
```  
  
 реализует индексатор в интерфейсе `ICitizen`.  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Индексаторы](../../../csharp/programming-guide/indexers/index.md)  
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)
