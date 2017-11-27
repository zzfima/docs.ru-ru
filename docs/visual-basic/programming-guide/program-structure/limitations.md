---
title: "Ограничения в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 97a2e162b9f1a673fbe805a5d2ef1421cd423a4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="visual-basic-limitations"></a>Ограничения в Visual Basic
Более ранних версиях [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] накладывались ограничения на код, например длина имени переменной, количество переменных, разрешенных в модуле и размер модуля. В Visual Basic .NET эти ограничения были ослаблены, предоставляя большую свободу в написании и упорядочении кода.  
  
 Физические ограничения зависят больше от памяти времени выполнения, чем на вопросы во время компиляции. Если следовать разумным правилам программирования и разделять большие приложения на несколько классов и модулей, то имеется очень мало вероятность возникновения внутреннего [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ограничение.  
  
 Ниже приведены некоторые ограничения, которые могут возникнуть в крайних случаях.  
  
-   **Длина имени.** Нет максимальное количество символов в имени каждого объявленного элемента программирования. Этот максимум применяется к полной уточняющей строке, если полное имя элемента. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Длина строки.** Имеется более 65 535 знаков в физической строке исходного кода. Логическая строка исходного кода может быть больше, если вы используете символы продолжения строки. В разделе [как: разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Размерность массива.** Имеется максимальное число измерений, которые можно объявить для массива. Это ограничивает количество индексов, которые можно использовать для указания элемента массива. В разделе [массива измерений в Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Длина строки.** Нет максимальное количество символов Юникода, которые можно хранить в одной строке. В разделе [строковый тип данных](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Длина строки в среде.** Нет до 32768 символов для любой строки среды, используется в качестве аргумента командной строки. Это ограничение для всех платформ.  
  
## <a name="see-also"></a>См. также  
 [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
