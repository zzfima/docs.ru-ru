---
title: Практическое руководство. Создание строк с помощью StringBuilder в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 00fefcc138164288d872cd339f165dc6ffc0131a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834196"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Практическое руководство. Создание строк с помощью StringBuilder в Visual Basic
В этом примере создается длинная строка из множества маленьких строк с помощью <xref:System.Text.StringBuilder> класса. <xref:System.Text.StringBuilder> Класс является более эффективным, чем `&=` оператор для объединения большого количества строк.  
  
## <a name="example"></a>Пример  
 В следующем примере создается экземпляр <xref:System.Text.StringBuilder> класс, прибавляется 1 000 строк к этому экземпляру, а затем возвращает его строковое представление.  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a>См. также

- [Using the StringBuilder class](../../../../standard/base-types/stringbuilder.md) (Использование класса StringBuilder)
- [Оператор &=](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Создание строк](../../../../standard/base-types/creating-new.md)
- [Операции со строками](../../../../standard/base-types/manipulating-strings.md)
