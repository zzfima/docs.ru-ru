---
title: Nothing и строки
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: dfc43748d0754f0a6a29763c42ab82d9937f89f8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344298"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing и строки в Visual Basic
Среда выполнения Visual Basic и .NET Framework оценивают `Nothing` по-разному, когда речь идет о строках.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Среда выполнения Visual Basic и .NET Framework  
 Рассмотрим следующий пример.  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Visual Basic среда выполнения обычно вычисляет `Nothing` как пустую строку (""). Однако .NET Framework не создает исключение, когда выполняется попытка выполнить операцию со строкой в `Nothing`.  
  
## <a name="see-also"></a>См. также:

- [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
