---
title: "Практическое руководство. Создание строки с помощью StringBuilder в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9def5da754d9075a8b498ac80e624caae5c97b96
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Практическое руководство. Создание строки с помощью StringBuilder в Visual Basic
В этом примере создается длинная строка из множества маленьких строк с помощью <xref:System.Text.StringBuilder> класса. <xref:System.Text.StringBuilder> Класс является более эффективным, чем `&=` оператора для сложения нескольких строк.  
  
## <a name="example"></a>Пример  
 В следующем примере создается экземпляр <xref:System.Text.StringBuilder> прибавляется 1 000 строк к этому экземпляру класса и возвращает его строковое представление.  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Using the StringBuilder class](../../../../standard/base-types/stringbuilder.md) (Использование класса StringBuilder)  
 [Оператор &=](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [Создание строк](../../../../standard/base-types/creating-new.md)  
 [Операции со строками](../../../../standard/base-types/manipulating-strings.md)  
 [Пример строк](http://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02)
