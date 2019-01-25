---
title: Nothing и строки в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 65a69861c2a74a3191a45eb782a97f289b0c0726
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574174"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing и строки в Visual Basic
Среда выполнения Visual Basic и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] оценки `Nothing` по-разному когда доходит до строки.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Среда выполнения Visual Basic и .NET Framework  
 Рассмотрим следующий пример.  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 Среда выполнения Visual Basic обычно оценивает `Nothing` как пустая строка (»»). [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] — Нет, тем не менее и создает исключение каждый раз, когда предпринята попытка выполнения операции строк на `Nothing`.  
  
## <a name="see-also"></a>См. также
- [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
