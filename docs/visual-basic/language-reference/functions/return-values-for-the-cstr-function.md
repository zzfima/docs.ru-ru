---
title: Возвращаемые значения функции CStr (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: 5312734633eea12aacd7e61afba616d31e06cd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Возвращаемые значения функции CStr (Visual Basic)
В следующей таблице описаны возвращаемые значения для `CStr` для различных типов данных из `expression`.  
  
|Если `expression` тип|Возвращаемые значения `CStr`|  
|-----------------------------|--------------------|  
|[Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Строка, содержащая «True» или «False».|  
|[Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|Строка, содержащая `Date` значение (Дата и время) в формате короткой даты системы.|  
|[Числовые типы данных](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Строка, содержащая число.|  
  
## <a name="cstr-and-date"></a>CStr и даты  
 `Date` Типа всегда содержит сведения о дате и времени. В целях преобразования типов Visual Basic рассматривает 1/1/0001 (1 января 1 года) быть *нейтральным значением* для даты и 00:00:00 (полночь) будет нейтральным значением времени. `CStr` не включает нейтральные значения в результирующую строку. Например, если вы преобразуете `#January 1, 0001 9:30:00#` в строку, результат будет «9:30:00 AM»; дата отбрасывается. Тем не менее, сведения о дате по-прежнему присутствует в исходной коллекции `Date` значение и может быть восстановлен с помощью функции например <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
> [!NOTE]
>  `CStr` Функция выполняет преобразование на основе текущих параметров языка и региональных параметров для приложения. Чтобы получить строковое представление числа в определенного языка и региональных параметров, используйте число `ToString(IFormatProvider)` метод. Например, использовать <xref:System.Double.ToString%2A?displayProperty=nameWithType> при преобразовании значения типа `Double` для `String`.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md)
