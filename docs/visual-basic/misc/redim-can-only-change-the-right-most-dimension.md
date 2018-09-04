---
title: '&#39;ReDim&#39; можно изменять только крайнее правое измерение'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 94e0fe81f7e750a67943b68f2db700e3a7831da1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502590"
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a>&#39;ReDim&#39; можно изменять только крайнее правое измерение
В операторе `ReDim` ключевое слово `Preserve` используется для изменения измерения массива, которое не является его последним измерением. При использовании `Preserve`можно изменять размер только последнего измерения массива. Для всех других измерений необходимо указать тот же размер, что и для существующего массива.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите ключевое слово `Preserve` .  
  
## <a name="see-also"></a>См. также  
 [Массивы в Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [Размерности массивов в Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [Оператор reDim](../../visual-basic/language-reference/statements/redim-statement.md)  
 [Оператор Dim](../../visual-basic/language-reference/statements/dim-statement.md)  
 [Preserve — удалено](https://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
