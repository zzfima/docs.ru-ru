---
title: "Таблица значений по умолчанию (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d609403269a5cbfe6715647a240c44b254a4d8f9
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="default-values-table-c-reference"></a>Таблица значений по умолчанию (Справочник по C#)
В следующей таблице показаны значения по умолчанию для типов значений, возвращаемых конструкторами по умолчанию. Конструкторы по умолчанию вызываются с помощью оператора `new`, как показано ниже:  
  
```  
int myInt = new int();  
```  
  
 Приведенная выше инструкция приводит к тому же результату, что и следующая:  
  
```  
int myInt = 0;  
```  
  
 Обратите внимание, что в C# не допускается использование неинициализированных переменных.  
  
|Тип значения|Значение по умолчанию|  
|----------------|-------------------|  
|[bool](../../../csharp/language-reference/keywords/bool.md)|`false`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|0|  
|[char](../../../csharp/language-reference/keywords/char.md)|'\0'|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|0,0M|  
|[double](../../../csharp/language-reference/keywords/double.md)|0,0D|  
|[enum](../../../csharp/language-reference/keywords/enum.md)|Значение, создаваемое выражением (E)0, где E — это идентификатор перечисления.|  
|[float](../../../csharp/language-reference/keywords/float.md)|0,0F|  
|[int](../../../csharp/language-reference/keywords/int.md)|0|  
|[long](../../../csharp/language-reference/keywords/long.md)|0L|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|0|  
|[short](../../../csharp/language-reference/keywords/short.md)|0|  
|[struct](../../../csharp/language-reference/keywords/struct.md)|Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|0|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|0|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|0|  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Таблица типов значений](../../../csharp/language-reference/keywords/value-types-table.md)   
 [Типы значений](../../../csharp/language-reference/keywords/value-types.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Справочные таблицы по типам](../../../csharp/language-reference/keywords/reference-tables-for-types.md)

