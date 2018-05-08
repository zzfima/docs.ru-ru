---
title: Предложение Alias (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 62b34f5860b35104b6a8caa82c359383999dd61b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="alias-clause-visual-basic"></a>Предложение Alias (Visual Basic)
Указывает, что внешняя процедура имеет другое имя в файле DLL.  
  
## <a name="remarks"></a>Примечания  
 `Alias` Ключевое слово может использоваться в этом контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 В следующем примере `Alias` ключевое слово используется для предоставления имени функции в advapi32.dll, `GetUserNameA`, которая `getUserName` используется вместо в этом примере. Функция `getUserName` вызывается в sub `getUser`, который отображает имя текущего пользователя.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
