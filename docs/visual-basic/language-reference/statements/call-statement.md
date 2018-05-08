---
title: Оператор Call (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 2074f44aedf59f1570e73c898a9bf64e57034923
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="call-statement-visual-basic"></a>Оператор Call (Visual Basic)
Передает управление `Function`, `Sub`, или процедуре библиотеки динамической компоновки (DLL).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Части  
 `procedureName`  
 Обязательно. Имя процедуры, которую необходимо вызвать.  
  
 `argumentList`  
 Необязательный. Список переменных или выражений, представляющих аргументы, передаваемые в процедуру при ее вызове. Несколько аргументов разделяются запятыми. При включении `argumentList`, его необходимо заключить в круглые скобки.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `Call` ключевое слово, при вызове процедуры. Для большинства вызовов процедур не должны использовать это ключевое слово.  
  
 Как правило, используется `Call` ключевое слово, если вызван выражение не начинается с идентификатора. Использование `Call` ключевое слово для других целей не рекомендуется.  
  
 Если процедура возвращает значение, `Call` инструкции отбрасывает ее.  
  
## <a name="example"></a>Пример  
 В следующем коде показано два примера где `Call` ключевое слово не требуется для вызова процедуры. В обоих примерах вызываемой выражение не начинается с идентификатора.  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
