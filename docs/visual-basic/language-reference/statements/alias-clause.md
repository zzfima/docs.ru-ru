---
title: "Предложение Alias (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Alias
helpviewer_keywords: Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f61e738434ea616d751576ef21669545afc41397
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
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
