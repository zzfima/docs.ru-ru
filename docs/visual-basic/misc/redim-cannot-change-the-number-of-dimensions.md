---
title: '&#39;Оператор reDim&#39; не может изменять число измерений'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: bfd4096141833b85a2126340ef549e1e1d1f8e3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39redim39-cannot-change-the-number-of-dimensions"></a>&#39;Оператор reDim&#39; не может изменять число измерений
Предпринята попытка использования оператора `ReDim` для изменения ранга (размерности) массива. Оператор`ReDim` может изменять размер одного или нескольких измерений массива, который уже был формально объявлен, но он не может изменить ранг массива.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что требуется изменить ранг, а не размеры массива, и по возможности используйте `Dim` для объявления нового массива с нужным рангом.  
  
## <a name="see-also"></a>См. также  
 [Массивы в Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [Размерности массивов в Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [Оператор reDim](../../visual-basic/language-reference/statements/redim-statement.md)  
 [Оператор Dim](../../visual-basic/language-reference/statements/dim-statement.md)
