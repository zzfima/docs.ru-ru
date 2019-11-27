---
title: Оператор Call
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 7de194ea23827e08c49f4519c1000708a4bd91b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350159"
---
# <a name="call-statement-visual-basic"></a>Оператор Call (Visual Basic)

Передает управление `Function`, `Sub`или процедуре библиотеки динамической компоновки (DLL).  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Части  

|||
|---|---|
|`procedureName`|Обязательно. Имя вызываемой процедуры.|
|`argumentList`|Необязательный элемент. Список переменных или выражений, представляющих аргументы, которые передаются в процедуру при ее вызове. Несколько аргументов разделяются запятыми. Если включить `argumentList`, необходимо заключить его в круглые скобки.|
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
