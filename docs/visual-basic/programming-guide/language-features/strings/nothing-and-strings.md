---
title: Nothing и строки в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: d03781209f0f9b021d540bd251c6c6025ad21422
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647197"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing и строки в Visual Basic
Среда выполнения Visual Basic и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] оценки `Nothing` по-разному когда дело доходит до строки.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Среда выполнения Visual Basic и .NET Framework  
 Рассмотрим следующий пример.  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 Среда выполнения Visual Basic обычно расценивает `Nothing` как пустая строка (»»). [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] — Нет, однако и создается исключение при попытке выполнить операцию строки на `Nothing`.  
  
## <a name="see-also"></a>См. также  
 [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
