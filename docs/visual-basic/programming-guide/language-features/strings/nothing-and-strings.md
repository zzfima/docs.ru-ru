---
title: Nothing и строки в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: f5c1ea8cc0728b25e8e874963967aed504e466d7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591342"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing и строки в Visual Basic
Среда выполнения Visual Basic и .NET Framework оценить `Nothing` по-разному когда доходит до строки.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Среда выполнения Visual Basic и .NET Framework  
 Рассмотрим следующий пример.  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Среда выполнения Visual Basic обычно оценивает `Nothing` как пустая строка (»»). .NET Framework — нет, тем не менее и создает исключение каждый раз, когда предпринята попытка выполнения операции строк на `Nothing`.  
  
## <a name="see-also"></a>См. также

- [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
