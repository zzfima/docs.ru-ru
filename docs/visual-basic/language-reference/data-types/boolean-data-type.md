---
title: Тип данных Boolean (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
ms.openlocfilehash: 00f77fe5e98099868e02d74fe1adc7690cb95cca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590281"
---
# <a name="boolean-data-type-visual-basic"></a>Тип данных Boolean (Visual Basic)
Содержит значения, которые могут быть только `True` или `False`. Ключевые слова `True` и `False` соответствуют двух состояний `Boolean` переменных.  
  
## <a name="remarks"></a>Примечания  
 Используйте [логический тип данных (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) содержит два значения состояния, например true или false, Да/Нет или Вкл/Выкл.  
  
 Значением свойства `Boolean` по умолчанию является `False`.  
  
 `Boolean` значения не хранятся в виде чисел, и хранимые значения не должны быть эквивалентными числам. Никогда не следует писать код, который основывается на эквивалентных числовых значениях для `True` и `False`. Когда это возможно, следует ограничить использование `Boolean` переменные с логическими значениями, для которых они предназначены.  
  
## <a name="type-conversions"></a>Преобразования типов  
 Когда Visual Basic преобразует числовые значения данных, тип `Boolean`, 0 становится `False` и все остальные значения становятся `True`. Когда Visual Basic преобразует `Boolean` значения в числовые типы `False` становится 0 и `True` становится 1.  
  
 При преобразовании между `Boolean` значения и числовые типы данных, следует помнить, что методы преобразования платформы .NET Framework не всегда производят те же результаты, как ключевые слова преобразования Visual Basic. Это так, как преобразование Visual Basic сохраняет поведение, совместимое с предыдущими версиями. Дополнительные сведения см. в разделе «Логическое тип Does не преобразования для числового типа точно» в [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="programming-tips"></a>Советы по программированию  
  
-   **Отрицательные числа.** `Boolean` не является числовым типом и не может представлять отрицательное значение. В любом случае не следует использовать `Boolean` для хранения числовых значений.  
  
-   **Символы типов.** `Boolean` не имеет знак типа литерала или знак типа идентификатора.  
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Boolean?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
 В следующем примере `runningVB` — `Boolean` переменной, которая хранит простой Да/нет.  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Boolean?displayProperty=nameWithType>  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)
