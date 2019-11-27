---
title: Оператор Throw
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
ms.openlocfilehash: 147345990b625e034e651e69b322bc098d0bd8de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352783"
---
# <a name="throw-statement-visual-basic"></a>Оператор Throw (Visual Basic)

Создает исключение в процедуре.

## <a name="syntax"></a>Синтаксис

```vb
Throw [ expression ]
```

## <a name="part"></a>Отделение

`expression`\
Предоставляет сведения о вызываемом исключении. Необязательно, если используется оператор `Catch`, в противном случае —.

## <a name="remarks"></a>Примечания

Оператор `Throw` создает исключение, которое можно обработать с помощью структурированного кода обработки исключений (`Try`...`Catch`...`Finally`) или неструктурированного кода обработки исключений (`On Error GoTo`). Можно использовать инструкцию `Throw` для перехвата ошибок в коде, поскольку Visual Basic перемещает стек вызовов до тех пор, пока не найдет соответствующий код обработки исключений.

Инструкцию `Throw` без выражения можно использовать только в инструкции `Catch`. в этом случае оператор повторно создает исключение, обрабатываемое в данный момент инструкцией `Catch`.

Оператор `Throw` сбрасывает стек вызовов для исключения `expression`. Если `expression` не указан, стек вызовов остается без изменений. Доступ к стеку вызовов для исключения можно получить с помощью свойства <xref:System.Exception.StackTrace%2A>.

## <a name="example"></a>Пример

Следующий код использует оператор `Throw` для создания исключения:

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a>См. также

- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
