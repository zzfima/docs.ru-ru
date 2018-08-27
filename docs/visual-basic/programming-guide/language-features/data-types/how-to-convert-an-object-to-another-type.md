---
title: Практическое руководство. Преобразование объекта к другому типу в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: f168b3021ee1dbe3c82edc22fc779767c30446b8
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42912017"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Практическое руководство. Преобразование объекта к другому типу в Visual Basic
Преобразования `Object` переменных в другой тип данных с помощью ключевого слова преобразования, например [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
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
  
 Если вы знаете, что содержимое `Object` переменной типа данных, лучше преобразовать в этот тип данных переменной. Если вы продолжите использовать `Object` переменной, то это вызовет либо *упаковки-преобразования* и *распаковки* (для типа значения) или *позднее связывание* (для ссылочного типа). Эти операции принимают дополнительное время выполнения и снижают производительность.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылка на пространство имен <xref:System?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Object>  
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Преобразования значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)  
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
