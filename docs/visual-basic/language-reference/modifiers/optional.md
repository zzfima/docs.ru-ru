---
title: Необязательно
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: a16dae35bf4bc84d95501624c4f023f390a8dda8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351440"
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)

Указывает, что аргумент процедуры может быть пропущен при вызове процедуры.

## <a name="remarks"></a>Примечания

Для каждого необязательного параметра необходимо указать константное выражение в качестве значения по умолчанию для этого параметра. Если результат вычисления выражения равен [Nothing](../../../visual-basic/language-reference/nothing.md), в качестве значения по умолчанию для параметра используется значение по умолчанию типа данных value.

Если список параметров содержит необязательный параметр, то каждый параметр, следующий за ним, также должен быть необязательным.

Модификатор `Optional` можно использовать в следующих контекстах:

- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)

- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)

- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)

> [!NOTE]
> При вызове процедуры с необязательными параметрами или без них можно передавать аргументы по положению или по имени. Дополнительные сведения см. в разделе [Передача аргументов по положению и по имени](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).

> [!NOTE]
> Можно также определить процедуру с необязательными параметрами с помощью перегрузки. Если имеется один необязательный параметр, можно определить две перегруженные версии процедуры, одна из которых принимает параметр, а другая — нет. Дополнительные сведения см. в разделе [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).

## <a name="example"></a>Пример

В следующем примере определяется процедура, имеющая необязательный параметр.

```vb
Public Function FindMatches(ByRef values As List(Of String),
                            ByVal searchString As String,
                            Optional ByVal matchCase As Boolean = False) As List(Of String)

    Dim results As IEnumerable(Of String)

    If matchCase Then
        results = From v In values
                  Where v.Contains(searchString)
    Else
        results = From v In values
                  Where UCase(v).Contains(UCase(searchString))
    End If

    Return results.ToList()
End Function
```

## <a name="example"></a>Пример

В следующем примере показано, как вызвать процедуру с аргументами, передаваемыми по положению, и с аргументами, передаваемыми по имени. Процедура имеет два необязательных параметра.

[!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]

## <a name="see-also"></a>См. также:

- [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
