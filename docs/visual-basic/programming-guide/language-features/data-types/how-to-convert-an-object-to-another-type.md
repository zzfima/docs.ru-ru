---
title: Практическое руководство. Преобразование объекта к другому типу в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 39083fc55d30e24c357ec162a15466f81655f4c8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582332"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Практическое руководство. Преобразование объекта к другому типу в Visual Basic
Преобразование `Object` переменной в другой тип данных осуществляется с помощью ключевого слова преобразования, например [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>Пример  
 В следующем примере переменная `Object` преобразуется в `Integer` и в `String`.  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Если известно, что содержимое переменной `Object` относится к определенному типу данных, лучше преобразовать переменную в этот тип данных. Если вы продолжаете использовать переменную `Object`, вы используете *упаковку* и распаковку (для типа значения) или *позднее связывание* *(для* ссылочного типа). Все эти операции занимают некоторое время и снижают производительность.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылка на пространство имен <xref:System?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Object>
- [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Преобразования значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
