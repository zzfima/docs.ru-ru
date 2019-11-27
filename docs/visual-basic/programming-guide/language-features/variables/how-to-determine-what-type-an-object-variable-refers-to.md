---
title: Практическое руководство. Определение типа, на который указывает объектная переменная
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 9f9b89e2fea0bd69cba6d50fa1d1fb9cc3927685
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348620"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Практическое руководство. Определение типа, на который указывает объектная переменная (Visual Basic)

Объектная переменная содержит указатель на данные, которые хранятся в других местах. Тип этих данных может изменяться во время выполнения. В любой момент можно использовать метод <xref:System.Type.GetTypeCode%2A> для определения текущего типа времени выполнения или [оператор typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md) , чтобы определить, совместим ли текущий тип времени выполнения с указанным типом.

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Определение точного типа объектной переменной, на которую в настоящее время ссылается

1. В объектной переменной вызовите метод <xref:System.Object.GetType%2A>, чтобы получить объект <xref:System.Type?displayProperty=nameWithType>.

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. В классе <xref:System.Type?displayProperty=nameWithType> вызовите общий метод <xref:System.Type.GetTypeCode%2A>, чтобы получить значение перечисления <xref:System.TypeCode> для типа объекта.

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    Можно проверить значение перечисления <xref:System.TypeCode> в отношении любого интересующего его члена, например `Double`.

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Определение, совместима ли тип объектной переменной с указанным типом

- Используйте оператор `TypeOf` в сочетании с [оператором is](../../../../visual-basic/language-reference/operators/is-operator.md) для проверки объекта с помощью выражения `TypeOf`...`Is`.

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    Выражение `TypeOf`...`Is` возвращает `True`, если тип времени выполнения объекта совместим с указанным типом.

    Критерий совместимости зависит от того, является ли указанный тип классом, структурой или интерфейсом. Как правило, типы являются совместимыми, если объект имеет тот же тип, что и, наследует от или реализует указанный тип. Дополнительные сведения см. в разделе [оператор typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md).

## <a name="compiling-the-code"></a>Компиляция кода

Обратите внимание, что указанный тип не может быть переменной или выражением. Это должно быть имя определенного типа, например класса, структуры или интерфейса. Сюда входят встроенные типы, такие как `Integer` и `String`.

## <a name="see-also"></a>См. также

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
