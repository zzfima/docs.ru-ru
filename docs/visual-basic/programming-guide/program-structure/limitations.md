---
title: Ограничения в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 57378c3aa18a5cc108c10e8654e55803f3cf9052
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649933"
---
# <a name="visual-basic-limitations"></a>Ограничения в Visual Basic
Более ранних версиях Visual Basic накладывались ограничения на код, например длина имени переменной, количество переменных в модуле и размер модуля. В Visual Basic .NET эти ограничения были ослаблены, предоставляя большую свободу в написании и упорядочении кода.  
  
 Физические ограничения зависят больше от памяти времени выполнения, чем на вопросы во время компиляции. Если следовать разумным правилам программирования и разделять большие приложения на несколько классов и модулей, имеется очень мало вероятность возникновения внутреннее ограничение Visual Basic.  
  
 Ниже приведены некоторые ограничения, которые могут возникнуть в крайних случаях.  
  
-   **Длина имени.** Нет максимальное количество символов в имени каждого объявленного элемента программирования. Этот максимум применяется к полной уточняющей строке, если полное имя элемента. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Длина строки.** Имеется более 65 535 знаков в физической строке исходного кода. Логическая строка исходного кода может быть больше, если вы используете символы продолжения строки. В разделе [как: разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Размерность массива.** Имеется максимальное число измерений, которые можно объявить для массива. Это ограничивает количество индексов, которые можно использовать для указания элемента массива. В разделе [массива измерений в Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Длина строки.** Нет максимальное количество символов Юникода, которые можно хранить в одной строке. В разделе [строковый тип данных](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Длина строки в среде.** Нет до 32768 символов для любой строки среды, используется в качестве аргумента командной строки. Это ограничение для всех платформ.  
  
## <a name="see-also"></a>См. также  
 [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
