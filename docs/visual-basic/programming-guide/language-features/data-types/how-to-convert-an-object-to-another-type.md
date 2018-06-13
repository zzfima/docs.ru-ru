---
title: Практическое руководство. Преобразование объекта к другому типу в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 367991e4bbca710df54edf73179f855ff79bb56e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647622"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Практическое руководство. Преобразование объекта к другому типу в Visual Basic
Преобразовать `Object` переменных в другой тип данных с помощью ключевого слова преобразования, например [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется преобразование `Object` переменной `Integer` и `String`.  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Если известно, что содержимое `Object` переменной определенного типа данных, лучше преобразовать переменную в этот тип данных. Если вы продолжаете использовать `Object` переменной, то это вызовет либо *упаковка-преобразование* и *распаковки* (для типа значения) или *позднего связывания* (для ссылочного типа). Эти операции принимают большего времени для выполнения и снижают производительность.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылка на пространство имен <xref:System?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Object>  
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Преобразования значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
