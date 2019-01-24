---
title: "\"ReDim\" может изменять только крайнее правое измерение"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 97eedabd550be397f9cdffc5fd864d7a88c30c31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714208"
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
- [Preserve — удалить](https://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
