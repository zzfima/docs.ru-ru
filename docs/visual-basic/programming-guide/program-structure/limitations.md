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
ms.openlocfilehash: 0f356b52304110299ed0af9bbccd5d03893f31a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596362"
---
# <a name="visual-basic-limitations"></a>Ограничения в Visual Basic
Более ранних версиях Visual Basic накладывались ограничения в коде, такое как длина имени переменной, количество переменных в модуле и размер модуля. В Visual Basic .NET эти ограничения были ослаблены, предоставляя большую свободу в написании и упорядочении кода.  
  
 Физические ограничения зависят больше памяти во время выполнения, чем на времени компиляции. Если вы используете оправданным приемов программирования и разделять большие приложения на несколько классов и модулей, то нет очень низкую вероятность возникновения внутреннее ограничение Visual Basic.  
  
 Ниже приведены некоторые ограничения, которые могут возникнуть в исключительных случаях.  
  
-   **Длина имени.** Есть максимальное число символов в имени каждого объявленного элемента программирования. Этот максимум применяется к полной уточняющей строке в том случае, если полное имя элемента. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Длина строки.** Можно использовать не более 65535 символов в физической строке исходного кода. Логическая строка исходного кода может быть больше времени, если вы используете символы продолжения строки. См. практическое руководство по [ Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Размерность массива.** Есть максимальное число измерений, которые можно объявить для массива. Это ограничивает количество индексов, которые можно использовать для указания элемента массива. См. в разделе [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Длина строки.** Есть максимальное число символов Юникода, которые можно хранить в одной строке. См. в разделе [строковый тип данных](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Длина строки в среде.** Есть более 32 768 символов для любой строки среды, используется в качестве аргумента командной строки. Это ограничение на всех платформах.  
  
## <a name="see-also"></a>См. также
- [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
