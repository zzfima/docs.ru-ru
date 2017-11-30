---
title: "Практическое руководство. Доступ к символам строк в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 54d604fc08dd97e0e31f9bcec148431374e8ef8f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Практическое руководство. Доступ к символам строк в Visual Basic
В этом примере демонстрируется использование <xref:System.String.Chars%2A> свойство для доступа к знаку в указанном месте в строке.  
  
## <a name="example"></a>Пример  
 Иногда полезно располагать сведениями о знаков в строки и позиции этих символов. Строку можно представить как массив символов (`Char` экземпляров); конкретного символа можно получить с помощью ссылки на индекс символа с помощью <xref:System.String.Chars%2A> свойство.  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 `index` Параметр <xref:System.String.Chars%2A> свойства начинается с нуля.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 <xref:System.String.Chars%2A> Свойство возвращает символ в указанной позиции. Тем не менее некоторые символы Юникода могут представляться на более чем один символ. Дополнительные сведения о том, как работать с символами Юникода см. в разделе [как: преобразование строкового значения в массиве символов](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 <xref:System.String.Chars%2A> Свойство выдает <xref:System.IndexOutOfRangeException> исключения Если `index` параметр больше или равным длине строки, или если он меньше нуля  
  
## <a name="see-also"></a>См. также  
 <xref:System.String.Chars%2A>  
 [Практическое руководство. Преобразование строки в массив символов](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)  
 [Преобразование между строками и другими типами данных в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)
