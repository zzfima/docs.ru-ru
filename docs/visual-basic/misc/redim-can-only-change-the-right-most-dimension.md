---
title: "\"ReDim\" может изменять только крайнее правое измерение"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 86d639e70e85b19a91f89fa4e0cab330af07dccf
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "58028816"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a>"ReDim" может изменять только крайнее правое измерение
В операторе `ReDim` ключевое слово `Preserve` используется для изменения измерения массива, которое не является его последним измерением. При использовании `Preserve`можно изменять размер только последнего измерения массива. Для всех других измерений необходимо указать тот же размер, что и для существующего массива.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите ключевое слово `Preserve` .  
  
## <a name="see-also"></a>См. также

- [Массивы в Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [Размерности массивов в Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [Оператор reDim](../../visual-basic/language-reference/statements/redim-statement.md)
- [Оператор Dim](../../visual-basic/language-reference/statements/dim-statement.md)
