---
title: "Сравнение свойств и индексаторов (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 102a6a97726fa19fcba0e6f19876a3935e8625f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a>Сравнение свойств и индексаторов (Руководство по программированию в C#)
Индексаторы подобны свойствам. К методам доступа индексаторов применяются те же правила, которые определены для методов доступа к свойствам, за исключением различий, показанных в следующей таблице.  
  
|Свойство|Индексатор|  
|--------------|-------------|  
|Позволяет вызывать методы как открытые члены данных.|Обеспечивает доступ к элементам внутренней коллекции объекта с использованием нотации массива для самого объекта.|  
|Доступ по простому имени.|Доступ посредством индекса.|  
|Может быть статическим членом или членом экземпляра.|Должен быть членом экземпляра.|  
|Метод доступа [get](../../../csharp/language-reference/keywords/get.md) свойства не имеет параметров.|Метод доступа `get` индексатора имеет тот же список формальных параметров, что и сам индексатор.|  
|Метод доступа [set](../../../csharp/language-reference/keywords/set.md) свойства содержит неявный параметр `value`.|Метод доступа `set` индексатора имеет тот же список формальных параметров, что и сам индексатор, и также должен содержать параметр [value](../../../csharp/language-reference/keywords/value.md).|  
|Поддерживает сокращенный синтаксис с использованием [автоматически реализуемых свойств](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).|Не поддерживает сокращенный синтаксис.|  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Индексаторы](../../../csharp/programming-guide/indexers/index.md)  
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)
