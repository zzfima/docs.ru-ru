---
title: Логический тип данных
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
ms.openlocfilehash: 5d05514207c5d07e81aab897f40f728570f6bd87
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347849"
---
# <a name="boolean-data-type-visual-basic"></a>Тип данных Boolean (Visual Basic)

Содержит значения, которые могут быть только `True` или `False`. Ключевые слова `True` и `False` соответствуют двум состояниям `Boolean` переменных.  
  
## <a name="remarks"></a>Примечания  

 Используйте [логический тип данных (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) для хранения двух значений, таких как true/false, да/нет или ON/OFF.  
  
 Значением свойства `Boolean` по умолчанию является `False`.  
  
 `Boolean` значения не хранятся в виде чисел, а хранимые значения не должны быть эквивалентны числам. Никогда не следует писать код, который использует эквивалентные числовые значения для `True` и `False`. Везде, где это возможно, следует ограничить использование переменных `Boolean` логическими значениями, для которых они предназначены.  
  
## <a name="type-conversions"></a>Преобразования типов  

 Когда Visual Basic преобразует числовые значения типа данных в `Boolean`, 0 становится `False` и все остальные значения становятся `True`. Когда Visual Basic преобразует `Boolean` значения в числовые типы, `False` преобразуется в 0, а `True` преобразуется в-1.  
  
 При преобразовании между `Boolean`ными значениями и числовыми типами данных помните, что методы преобразования .NET Framework не всегда дают те же результаты, что и ключевые слова для преобразования Visual Basic. Это обусловлено тем, что Visual Basicное преобразование поддерживает поведение, совместимое с предыдущими версиями. Дополнительные сведения см. в разделе "неверное Преобразование логического типа в числовой тип" раздела [Устранение неполадок типов данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="programming-tips"></a>Советы по программированию  
  
- **Отрицательные числа.** `Boolean` не является числовым типом и не может представлять отрицательное значение. В любом случае не следует использовать `Boolean` для хранения числовых значений.  
  
- **Символы типа.** `Boolean` не имеет символа типа литерала или символа типа идентификатора.  
  
- **Тип платформы.** В .NET Framework данный тип соответствует структуре <xref:System.Boolean?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  

 В следующем примере `runningVB` является переменной `Boolean`, в которой хранится простой параметр Да/нет.  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Boolean?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)
