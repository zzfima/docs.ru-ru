---
title: "Практическое руководство. Создание строки из значений массива символьного типа (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06e5c6923c26f3cb84b38475d6680523853d727d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Практическое руководство. Создание строки из значений массива символьного типа (Visual Basic)
Этот пример создает строку «abcd» из отдельных символов.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 У этого метода нет особых требований.  
  
 Синтаксис `"a"c`, где одному `c` соответствует отдельный символ в кавычки, используется для создания символьного литерала.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Символы NULL (эквивалентно `Chr(0)`) в строке могут привести к непредвиденным результатам при использовании этой строки. Символ null будет включен в строку, но символы, следующие за будет отображаться в некоторых ситуациях.  
  
## <a name="see-also"></a>См. также  
 <xref:System.String>  
 [Тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
