---
title: "struct (справочник по C#) | Microsoft Docs"
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
  - "struct_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "struct - ключевое слово [C#]"
  - "структуры [C#], struct - ключевое слово"
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# struct (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Тип `struct` представляет собой тип значения, который обычно используется для инкапсуляции небольших групп связанных переменных, например координат прямоугольника или характеристик элемента в инвентаризации.  В следующем примере показано простое объявление структуры:  
  
```  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## Заметки  
 Структуры также могут содержать [конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md), [константы](../../../csharp/programming-guide/classes-and-structs/constants.md), [поля](../../../csharp/programming-guide/classes-and-structs/fields.md), [методы](../../../csharp/programming-guide/classes-and-structs/methods.md), [свойства](../../../csharp/programming-guide/classes-and-structs/properties.md), [индексаторы](../../../csharp/programming-guide/indexers/index.md), [операторы](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [события](../../../csharp/programming-guide/events/index.md) и [вложенные типы](../../../csharp/programming-guide/classes-and-structs/nested-types.md), хотя, если требуется несколько таких членов, тип необходимо заменить классом.  
  
 Примеры содержатся в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
 Структуры могут реализовать интерфейс, но не могут наследоваться из другой структуры.  По этой причине члены структуры не могут объявляться как `protected`.  
  
 Для получения дополнительной информации см. [Структуры](../../../csharp/programming-guide/classes-and-structs/structs.md).  
  
## Примеры  
 Примеры см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
## Спецификация языка C\#  
 Примеры содержатся в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Типы](../../../csharp/language-reference/keywords/types.md)   
 [Типы значений](../../../csharp/language-reference/keywords/value-types.md)   
 [класс](../../../csharp/language-reference/keywords/class.md)   
 [интерфейс](../../../csharp/language-reference/keywords/interface.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)