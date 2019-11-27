---
title: Как преобразовать объект в другой тип
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 19708d03b0514f4572c2baa53e05781e5949766b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350075"
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
- [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
