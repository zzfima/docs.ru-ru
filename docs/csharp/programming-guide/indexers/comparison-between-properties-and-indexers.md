---
title: Руководство по программированию на C#. Сравнение свойств и индексаторов
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 053eb7ee0fe9333f049e5b4f8a8e709e42aa2119
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53234465"
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

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Индексаторы](../../../csharp/programming-guide/indexers/index.md)  
- [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)
