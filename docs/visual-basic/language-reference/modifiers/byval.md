---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c192cdb4ac43ad614fbfb663079c03ddc6c358c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Указывает, что аргумент передается таким образом, вызванная процедура или свойство не может изменить значение переменной, представляющей аргумент в вызывающем коде.  
  
## <a name="remarks"></a>Примечания  
 Модификатор `ByVal` можно использовать в следующих контекстах:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование `ByVal` механизм с ссылочным аргументом типа передачи параметров. В примере, — аргумент `c1`, экземпляр класса `Class1`. `ByVal`предотвращает изменение базовое значение аргумента ссылка кода в процедурах `c1`, но не защищает доступные поля и свойства `c1`.  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)  
 [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
