---
title: "Ограничения в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ограничения"
  - "ограничения, Visual Basic"
  - "пределы"
  - "пределы, код Visual Basic"
  - "код Visual Basic, ограничения"
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Ограничения в Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

В более ранних версиях [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] накладывались ограничения на такие параметры кода, как длина имени переменной, количество переменных в модуле и размер модуля.  В [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] эти ограничения были ослаблены, предоставляя большую свободу в написании и упорядочении кода.  
  
 Физические ограничения зависят больше от памяти времени выполнения, чем от времени компиляции.  Если следовать разумным правилам программирования и разделять большие приложения на несколько классов и модулей, то вероятность столкнуться с внутренними [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ограничениями очень мала.  
  
 Ниже перечислены некоторые ограничения, которые могут возникнуть в экстремальных случаях.  
  
-   **Длина имени.** Существует максимальное число знаков для имени каждого объявленного элемента программирования.  Этот максимум применяется к полной уточняющей строке, если имя элемента уточнено.  См. раздел [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Длина строки.** Максимальное количество символов в физической строке исходного кода составляет 65535 знаков.  При использовании символов продолжения строки логическая строка исходного кода может быть больше.  См. раздел [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Размерность массива.** Существует максимальная размерность массива, который можно объявить.  Это ограничивает количество индексов, которые можно использовать для указания элемента массива.  См. раздел [Размерность массивов в Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Длина строки.** Существует максимальное число знаков Юникода, которые можно хранить в одной строке.  См. раздел [Тип данных String](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Длина строки в среде.** Существует максимум 32768 знаков для любой строки среды, используемой в качестве аргумента командной строки.  Это ограничение для всех платформ.  
  
## См. также  
 [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)