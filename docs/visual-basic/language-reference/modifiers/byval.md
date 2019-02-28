---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: edee47e41ca78175a6fb24ed5eac255c03de0901
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972580"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Указывает, что аргумент передается таким образом, что вызванная процедура или свойство не может изменить значение переменной в аргументе в вызывающем коде.  
  
## <a name="remarks"></a>Примечания  
 Модификатор `ByVal` можно использовать в следующих контекстах:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование `ByVal` механизм с ссылочным аргументом типа передачи параметров. В примере аргумент является `c1`, экземпляр класса `Class1`. `ByVal` запрещает изменять основное значение ссылочного аргумента кода в процедурах `c1`, но не защищает доступные поля и свойства `c1`.  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a>См. также
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
