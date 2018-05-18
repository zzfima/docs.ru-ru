---
title: struct (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 5a4863bc93a115d14e791509f99b7b13bee9f68f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="struct-c-reference"></a>struct (справочник по C#)
Тип `struct` представляет собой тип значения, который обычно используется для инкапсуляции небольших групп связанных переменных, например координат прямоугольника или характеристик элемента в инвентаризации. В следующем примере показано простое объявление структуры:  
  
```  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a>Примечания  
 Структуры также могут содержать [конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md), [константы](../../../csharp/programming-guide/classes-and-structs/constants.md), [поля](../../../csharp/programming-guide/classes-and-structs/fields.md), [методы](../../../csharp/programming-guide/classes-and-structs/methods.md), [свойства](../../../csharp/programming-guide/classes-and-structs/properties.md), [индексаторы](../../../csharp/programming-guide/indexers/index.md), [операторы](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [события](../../../csharp/programming-guide/events/index.md) и [вложенные типы](../../../csharp/programming-guide/classes-and-structs/nested-types.md), хотя, если требуется несколько таких членов, тип необходимо заменить классом.  
  
 Примеры см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
 Структуры могут реализовать интерфейс, но не могут наследоваться из другой структуры. По этой причине члены структуры не могут объявляться как `protected`.  
  
 Дополнительные сведения см. в разделе [Структуры](../../../csharp/programming-guide/classes-and-structs/structs.md).  
  
## <a name="examples"></a>Примеры  
 Примеры и дополнительные сведения см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 Примеры см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md)  
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Типы](../../../csharp/language-reference/keywords/types.md)  
 [Типы значений](../../../csharp/language-reference/keywords/value-types.md)  
 [class](../../../csharp/language-reference/keywords/class.md)  
 [interface](../../../csharp/language-reference/keywords/interface.md)  
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)
