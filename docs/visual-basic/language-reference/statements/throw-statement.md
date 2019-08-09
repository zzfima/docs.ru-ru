---
title: Оператор Throw (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 9680700267f17c8e316de351fead61f1dc4aded0
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68869021"
---
# <a name="throw-statement-visual-basic"></a>Оператор Throw (Visual Basic)

Создает исключение в процедуре.

## <a name="syntax"></a>Синтаксис

```vb
Throw [ expression ]
```

## <a name="part"></a>Отделение

`expression`\
Предоставляет сведения о вызываемом исключении. Необязательно, если размещен в `Catch` операторе, в противном случае является обязательным.

## <a name="remarks"></a>Примечания

Оператор создает исключение, которое можно обработать с помощью структурированного кода обработки исключений (`Try`... `Throw` `Catch`... ) или неструктурированный код обработки исключений (`On Error GoTo`). `Finally` Можно использовать `Throw` инструкцию для перехвата ошибок в коде, так как Visual Basic перемещается вверх по стеку вызовов до тех пор, пока не найдет соответствующий код обработки исключений.

Инструкцию без выражения можно использовать только `Catch` в операторе, в этом случае инструкция повторно создает исключение, которое `Catch` в настоящее время обрабатывается инструкцией. `Throw`

Инструкция сбрасывает стек вызовов `expression` для исключения. `Throw` Если `expression` параметр не указан, стек вызовов остается без изменений. Доступ к стеку вызовов для исключения можно получить с помощью <xref:System.Exception.StackTrace%2A> свойства.

## <a name="example"></a>Пример

Следующий код использует `Throw` инструкцию для создания исключения:

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a>См. также

- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
