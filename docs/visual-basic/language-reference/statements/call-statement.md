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
ms.openlocfilehash: a04ebddc7db176188876da1082e1e6946e1e8eec
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005167"
---
# <a name="call-statement-visual-basic"></a>Оператор Call (Visual Basic)

Передает управление в процедуру `Function`, `Sub` или в библиотеку динамической компоновки (DLL).  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Части  

|||
|---|---|
|`procedureName`|Обязательный. Имя вызываемой процедуры.|
|`argumentList`|Необязательный параметр. Список переменных или выражений, представляющих аргументы, которые передаются в процедуру при ее вызове. Несколько аргументов разделяются запятыми. Если включить `argumentList`, необходимо заключить его в круглые скобки.|
|||
  
## <a name="remarks"></a>Примечания

 При вызове процедуры можно использовать ключевое слово `Call`. Для большинства вызовов процедур использовать это ключевое слово не обязательно.

 Обычно используется ключевое слово `Call`, если вызванное выражение не начинается с идентификатора. Использование ключевого слова `Call` для других целей не рекомендуется.

 Если процедура возвращает значение, то инструкция `Call` отклоняет ее.

## <a name="example"></a>Пример

 В следующем коде показаны два примера, где ключевое слово `Call` необходимо для вызова процедуры. В обоих примерах вызванное выражение не начинается с идентификатора.

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a>См. также

- [Оператор Function](function-statement.md)
- [Оператор Sub](sub-statement.md)
- [Оператор Declare](declare-statement.md)
- [Лямбда-выражения](../../programming-guide/language-features/procedures/lambda-expressions.md)
