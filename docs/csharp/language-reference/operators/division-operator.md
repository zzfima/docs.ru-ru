---
title: Оператор / (Справочник по C#)
ms.date: 04/04/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 9d0bbff1fd9f4ab3c93c879d12ccd5fde1187b44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272575"
---
# <a name="-operator-c-reference"></a>Оператор / (Справочник по C#)
Оператор деления (`/`) делит первый операнд на второй. Все числовые типы имеют предопределенные операторы деления.
  
## <a name="remarks"></a>Примечания  
 Определяемые пользователем типы могут вызвать перегрузку оператора `/` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) . Перегрузка оператора `/` неявно перегружает [ оператор /= ](division-assignment-operator.md).  
  
 При делении двух целых чисел результат всегда является целочисленным. Например, результат 7 / 3 равняется 2. Эту операцию не следует путать с делением с округлением к меньшему, так как оператор `/` производит округление в торону нуля: –7/3 равно –2.  
  
 Чтобы получить частное в виде рационального числа, используйте тип `float`, `double` или `decimal`. Существует множество способов преобразования между [встроенными числовыми типами](../../../csharp/language-reference/keywords/reference-tables-for-types.md).  
  
 Чтобы определить остаток, используйте [оператор остатка](../../../csharp/language-reference/operators/remainder-operator.md) (`%`).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
