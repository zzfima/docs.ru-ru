---
title: Default (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: 555e15110c7af501de05d1f395a72ca4b7800054
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Определяет свойство как свойство по умолчанию для класса, структуры или интерфейса.  
  
## <a name="remarks"></a>Примечания  
 Класса, структуры или интерфейса можно указать не более одного из его свойств, как *свойство по умолчанию*, если это свойство принимает хотя бы один параметр. Если код ссылается на класс или структуру без указания члена, Visual Basic устраняет эту ссылку на свойство по умолчанию.  
  
 Свойства по умолчанию может привести к небольшому сокращению символы исходного кода, но они могут сделать код более сложным для восприятия. Если вызывающий код не знаком с класса или структуры, когда он ссылается на имя класса или структуры, его невозможно точно определить ли такая ссылка обращается к классу или структуре или свойство по умолчанию. Это может привести к ошибкам компилятора или ошибки слабая логики времени выполнения.  
  
 Можно частично уменьшить вероятность ошибок, связанных с свойство по умолчанию с помощью всегда [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) для компилятора тип проверки `On`.  
  
 Если вы планируете использовать предварительно определенный класс или структуру в коде, необходимо определить, имеет ли он свойство по умолчанию и если да, то, что ее имя —.  
  
 Из-за эти недостатки можно не определять свойства по умолчанию. Для удобства чтения кода следует также учитывать всегда ссылается на все свойства явным образом, даже свойства по умолчанию.  
  
 `Default` Модификатор может использоваться в этом контексте:  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>См. также  
 [Как: объявление и вызов свойства по умолчанию в Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
