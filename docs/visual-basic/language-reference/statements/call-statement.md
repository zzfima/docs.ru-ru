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
ms.openlocfilehash: 259fcc6f1c59df09e768a08204df81aa8105de53
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936793"
---
# <a name="call-statement-visual-basic"></a>Оператор Call (Visual Basic)
Передает управление `Function`, `Sub`, или процедуре библиотеки динамической компоновки (DLL).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Части  
|||
|---|---|
|`procedureName`|Обязательно. Имя процедуры.|
|`argumentList`|Необязательный. Список переменных или выражений, представляющих аргументы, передаваемые в процедуру при ее вызове. Несколько аргументов разделяются запятыми. При включении `argumentList`, его необходимо заключить в круглые скобки.|
|||
  
## <a name="remarks"></a>Примечания  
 Можно использовать `Call` ключевое слово при вызове процедуры. Для большинства вызовов процедур не нужно использовать это ключевое слово.  
  
 Как правило, используется `Call` ключевое слово, если вызываемый выражение не начинается с идентификатора. Использование `Call` ключевое слово для других целей не рекомендуется.  
  
 Если процедура возвращает значение, `Call` инструкции отклоняет его.  
  
## <a name="example"></a>Пример  
 В следующем коде показано два примера где `Call` ключевое слово не требуется для вызова процедуры. В обоих примерах вызываемой выражение не начинается с идентификатора.  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
