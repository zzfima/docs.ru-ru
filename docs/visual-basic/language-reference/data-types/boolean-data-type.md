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
ms.openlocfilehash: 7b64302d801a08f976de0ec969983c821f7a8471
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796998"
---
# <a name="boolean-data-type-visual-basic"></a>Тип данных Boolean (Visual Basic)
Содержит значения, которые могут быть только `True` или `False`. Ключевые слова `True` и `False` соответствуют двух состояний `Boolean` переменные.  
  
## <a name="remarks"></a>Примечания  
 Используйте [логический тип данных (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) должен содержать два значения состояния, такие как true или false, Да/Нет, или Вкл/Выкл.  
  
 Значением свойства `Boolean` по умолчанию является `False`.  
  
 `Boolean` значения не хранятся в виде чисел, и хранимые значения не предназначены как эквивалент чисел. Никогда не следует писать код, основанный на эквивалентных числовых значений для `True` и `False`. Когда это возможно, следует ограничить использование `Boolean` переменные с логическими значениями, для которых они предназначены.  
  
## <a name="type-conversions"></a>Преобразования типов  
 Когда Visual Basic преобразует значения типа числовых данных в `Boolean`, становится 0 `False` и все остальные значения становятся `True`. Когда Visual Basic преобразует `Boolean` значения к числовому, `False` становится 0 и `True` становится 1.  
  
 При преобразовании между `Boolean` значения и числовые типы данных, имейте в виду, что методы преобразования платформы .NET Framework не всегда производят те же результаты, что ключевые слова преобразований Visual Basic. Это обусловлено преобразование Visual Basic сохраняет поведение, совместимое с предыдущими версиями. Дополнительные сведения см. в разделе «Логическое тип Does не преобразования для числового типа точно» в [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="programming-tips"></a>Советы по программированию  
  
- **Отрицательные числа.** `Boolean` не является числовым типом и не может представлять отрицательное значение. В любом случае не следует использовать `Boolean` для хранения числовых значений.  
  
- **Символы типа.** `Boolean` не имеет знак типа литерала или знак типа идентификатора.  
  
- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Boolean?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
 В следующем примере `runningVB` является `Boolean` переменной, которая хранит простой Да/нет.  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Boolean?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)
