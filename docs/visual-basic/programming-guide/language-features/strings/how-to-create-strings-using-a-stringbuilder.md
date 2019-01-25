---
title: Как выполнить Создание строк с помощью StringBuilder в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 84f0f41cf8ee23466d47dae3b1068c3bc5334072
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528450"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Как выполнить Создание строк с помощью StringBuilder в Visual Basic
В этом примере создается длинная строка из множества маленьких строк с помощью <xref:System.Text.StringBuilder> класса. <xref:System.Text.StringBuilder> Класс является более эффективным, чем `&=` оператор для объединения большого количества строк.  
  
## <a name="example"></a>Пример  
 В следующем примере создается экземпляр <xref:System.Text.StringBuilder> класс, прибавляется 1 000 строк к этому экземпляру, а затем возвращает его строковое представление.  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a>См. также
- [Using the StringBuilder class](../../../../standard/base-types/stringbuilder.md) (Использование класса StringBuilder)
- [Оператор &=](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Создание строк](../../../../standard/base-types/creating-new.md)
- [Операции со строками](../../../../standard/base-types/manipulating-strings.md)
- [Пример строк](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))
