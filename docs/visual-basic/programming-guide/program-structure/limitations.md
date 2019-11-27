---
title: Ограничения
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: f7e19977a011565bb4b1536af5cab195f8a01017
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347372"
---
# <a name="visual-basic-limitations"></a>Ограничения в Visual Basic
Более ранние версии Visual Basic принудительно применяют границы кода, такие как длина имен переменных, количество переменных, допустимых в модулях, и размер модуля. В Visual Basic .NET эти ограничения были ослаблены, что обеспечивает большую свободу при написании и упорядочении кода.  
  
 Физические ограничения зависят больше от объема памяти во время выполнения, чем в вопросах времени компиляции. Если вы используете разумные методики программирования и разбиваете крупные приложения на несколько классов и модулей, то вероятность возникновения внутренних ограничений на Visual Basic невелика.  
  
 Ниже перечислены некоторые ограничения, которые могут возникнуть в экстремальных случаях.  
  
- **Длина имени.** Существует максимальное число символов в имени каждого объявленного программного элемента. Это максимальное значение применяется ко всей уточняющей строке, если имя элемента является полным. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
- **Длина строки.** В физической строке исходного кода содержится не более 65535 символов. Логическая строка исходного кода может быть длиннее, если используются символы продолжения строки. См. раздел [как разрывать и объединять операторы в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
- **Размеры массива.** Существует максимальное количество измерений, которые можно объявить для массива. Это ограничивает количество индексов, которые можно использовать для указания элемента массива. См. раздел [измерения массива в Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
- **Длина строки.** Существует максимальное число символов Юникода, которые можно хранить в одной строке. См. [строковый тип данных](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
- **Длина строки окружения.** Для любой строки среды, используемой в качестве аргумента командной строки, можно использовать не более 32768 символов. Это ограничение на всех платформах.  
  
## <a name="see-also"></a>См. также

- [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Соглашения об именовании Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
