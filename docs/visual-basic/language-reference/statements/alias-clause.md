---
title: Предложение Alias (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 9cf97402d0b0a6cd16dd75a970c1d29a2fcc30a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498574"
---
# <a name="alias-clause-visual-basic"></a>Предложение Alias (Visual Basic)
Указывает, что внешняя процедура имеет другое имя в файле DLL.  
  
## <a name="remarks"></a>Примечания  
 `Alias` Слово может использоваться в этом контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 В следующем примере `Alias` ключевое слово используется для предоставления имени функции в advapi32.dll, `GetUserNameA`, в котором `getUserName` используется вместо параметра в этом примере. Функция `getUserName` вызывается в sub `getUser`, который отображает имя текущего пользователя.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a>См. также
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
