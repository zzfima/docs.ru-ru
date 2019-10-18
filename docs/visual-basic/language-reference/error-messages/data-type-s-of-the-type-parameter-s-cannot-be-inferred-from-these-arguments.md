---
title: Типы данных параметров-типов не могут быть определены из этих аргументов
ms.date: 07/20/2015
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
ms.openlocfilehash: 97b03874489473482554078958c7bfd29d87c095
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523991"
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a>Типы данных параметров-типов не могут быть определены из этих аргументов

Типы данных параметров типа не могут выводиться из этих аргументов. Явное указание типов данных может исправить эту ошибку.

Эта ошибка возникает при неудачном разрешении перегрузки. Ошибка появляется в виде сообщения, в котором указывается, почему была исключена определенная потенциальная перегрузка. В сообщении об ошибке объясняется, что компилятор не может использовать определение типа для поиска типов данных для параметров типа.

> [!NOTE]
> Когда указание аргументов является обязательным (например, в операторах выражений запросов), это сообщение об ошибке появляется без второй фразы.

Эта ошибка показана в приведенном ниже коде.

```vb
Module Module1

    Sub Main()

        '' Not Valid.
        'OverloadedGenericMethod("Hello", "World")

    End Sub

    Sub OverloadedGenericMethod(Of T)(ByVal x As String,
                                      ByVal y As InterfaceExample(Of T))
    End Sub

    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,
                                         ByVal y As InterfaceExample(Of R))
    End Sub

End Module

Interface InterfaceExample(Of T)
End Interface
```

**Идентификатор ошибки:** BC36647 и BC36644

## <a name="to-correct-this-error"></a>Исправление ошибки

Попробуйте указать тип данных для параметра или параметров типа, вместо того чтобы полагаться на определение типа.

## <a name="see-also"></a>См. также

- [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Generic Procedures in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [Преобразования типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
