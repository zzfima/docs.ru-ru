---
title: '&#39; ReDim &#39; не может изменять число измерений'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8cf3713c72bd07803935065780e894c130911a6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39redim39-cannot-change-the-number-of-dimensions"></a>&#39; ReDim &#39; не может изменять число измерений
Предпринята попытка использования оператора `ReDim` для изменения ранга (размерности) массива. Оператор`ReDim` может изменять размер одного или нескольких измерений массива, который уже был формально объявлен, но он не может изменить ранг массива.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что требуется изменить ранг, а не размеры массива, и по возможности используйте `Dim` для объявления нового массива с нужным рангом.  
  
## <a name="see-also"></a>См. также  
 [Массивы в Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [Размерности массивов в Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [Оператор reDim](../../visual-basic/language-reference/statements/redim-statement.md)  
 [Оператор Dim](../../visual-basic/language-reference/statements/dim-statement.md)
