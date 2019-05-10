---
title: ReDim не может изменять размерность
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 1e9695bbc7f104aa741de232f1f6d3c76df2cebf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591748"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>ReDim не может изменять размерность
Предпринята попытка использования оператора `ReDim` для изменения ранга (размерности) массива. Оператор`ReDim` может изменять размер одного или нескольких измерений массива, который уже был формально объявлен, но он не может изменить ранг массива.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Убедитесь, что требуется изменить ранг, а не размеры массива, и по возможности используйте `Dim` для объявления нового массива с нужным рангом.  
  
## <a name="see-also"></a>См. также

- [Массивы в Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [Размерности массивов в Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [Оператор reDim](../../visual-basic/language-reference/statements/redim-statement.md)
- [Оператор Dim](../../visual-basic/language-reference/statements/dim-statement.md)
