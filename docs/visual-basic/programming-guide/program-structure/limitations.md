---
title: "Ограничения в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- limits
- limitations, Visual Basic
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d556b045b4ebae6ba24c0571a6cb7e5337c6a8f2
ms.lasthandoff: 03/13/2017

---
# <a name="visual-basic-limitations"></a>Ограничения в Visual Basic
Более ранние версии [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] накладывались ограничения на код, такие как длина имени переменной, разрешенное количество переменных в модуле и размер модуля. В [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], эти ограничения были ослаблены, предоставляя большую свободу в написании и упорядочении кода.  
  
 Физические ограничения зависят больше от памяти времени выполнения, чем на времени компиляции. Если следовать разумным правилам программирования и разделять большие приложения на несколько классов и модулей, то есть очень низкую вероятность возникновения внутреннего [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ограничение.  
  
 Ниже приведены некоторые ограничения, которые могут возникнуть в крайних случаях.  
  
-   **Длина имени.** Существует максимальное число знаков для имени каждого объявленного элемента программирования. Этот максимум применяется к полной уточняющей строке, если полное имя элемента. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Длина строки.** Существует более 65535 символов в физической строке исходного кода. Логическая строка исходного кода может быть больше, если вы используете символы продолжения строки. В разделе [как: разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Размерность массива.** Существует максимальное число измерений, которые можно объявить для массива. Это ограничивает количество индексов, которые можно использовать для указания элемента массива. В разделе [массива измерений в Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Длина строки.** Существует максимальное число знаков Юникода, которые можно хранить в одной строке. В разделе [строковый тип данных](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Длина строки в среде.** Существует максимум 32768 знаков для любой строки среды, используется в качестве аргумента командной строки. Это ограничение для всех платформ.  
  
## <a name="see-also"></a>См. также  
 [Структура программы и соглашения о коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
