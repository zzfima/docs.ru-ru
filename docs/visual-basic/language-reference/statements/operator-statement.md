---
title: Оператор Operator
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: aa6ae3977977ded05e47d12dabe72f09251f262d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353798"
---
# <a name="operator-statement"></a>Оператор Operator

Объявляет символ оператора, операнды и код, определяющие процедуру оператора для класса или структуры.

## <a name="syntax"></a>Синтаксис

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a>Части

`attrlist`  
Необязательно. См. [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).

`Public`  
Обязательное. Указывает, что эта процедура оператора имеет [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступ.

`Overloads`  
Необязательно. См. раздел [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).

`Shared`  
Обязательное. Указывает, что эта процедура оператора является [общей](../../../visual-basic/language-reference/modifiers/shared.md) процедурой.

`Shadows`  
Необязательно. См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).

`Widening`  
Требуется для оператора преобразования, если не указано `Narrowing`. Указывает, что эта процедура оператора определяет [расширяющее](../../../visual-basic/language-reference/modifiers/widening.md) преобразование. См. раздел "расширяющие и сужающие преобразования" на этой странице справки.

`Narrowing`  
Требуется для оператора преобразования, если не указано `Widening`. Указывает, что эта процедура оператора определяет [понижающие](../../../visual-basic/language-reference/modifiers/narrowing.md) преобразования. См. раздел "расширяющие и сужающие преобразования" на этой странице справки.

`operatorsymbol`  
Обязательное. Символ или идентификатор оператора, определяемого данной процедурой оператора.

`operand1`  
Обязательное. Имя и тип одного операнда унарного оператора (включая оператор преобразования) или левого операнда бинарного оператора.

`operand2`  
Требуется для бинарных операторов. Имя и тип правого операнда бинарного оператора.

`operand1` и `operand2` имеют следующие синтаксис и части:

`[ ByVal ] operandname [ As operandtype ]`

|Отделение|Описание|
|----------|-----------------|
|`ByVal`|Необязательно, но механизм передачи должен быть [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).|
|`operandname`|Обязательное. Имя переменной, представляющей этот операнд. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|
|`operandtype`|Необязательно, если не `On``Option Strict`. Тип данных этого операнда.|

`type`  
Необязательно, если не `On``Option Strict`. Тип данных значения, возвращаемого процедурой оператора.

`statements`  
Необязательно. Блок инструкций, выполняемых процедурой оператора.

`returnvalue`  
Обязательное. Значение, возвращаемое процедурой оператора в вызывающий код.

`End` `Operator`  
Обязательное. Завершает определение этой процедуры оператора.

## <a name="remarks"></a>Примечания

`Operator` можно использовать только в классе или структуре. Это означает, что *контекст объявления* для оператора не может быть исходным файлом, пространством имен, модулем, интерфейсом, процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

Все операторы должны быть `Public Shared`. Для любого операнда нельзя указать `ByRef`, `Optional`или `ParamArray`.

Нельзя использовать символ оператора или идентификатор для хранения возвращаемого значения. Необходимо использовать оператор `Return` и указать значение. Любое количество инструкций `Return` может находиться в любом месте процедуры.

Определение оператора таким образом называется *перегрузкой оператора*, независимо от того, используется ли ключевое слово `Overloads`. В приведенной ниже таблице перечислены операторы, которые можно определить.

|Тип|Операторы|
|----------|---------------|
|Унарный|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|Преобразование (унарный)|`CType`|

Обратите внимание, что оператор `=` в списке binary является оператором сравнения, а не оператором присваивания.

При определении `CType`необходимо указать либо `Widening`, либо `Narrowing`.

## <a name="matched-pairs"></a>Парные пары

Необходимо определить определенные операторы в качестве совпадающих пар. При определении любого из этих двух операторов такой пары необходимо определить и другое. Сопоставленные пары являются следующими:

- `=` и `<>`

- `>` и `<`

- `>=` и `<=`

- `IsTrue` и `IsFalse`

## <a name="data-type-restrictions"></a>Ограничения типов данных

Каждый определяемый оператор должен содержать класс или структуру, в которых он определен. Это означает, что класс или структура должны выглядеть как тип данных следующего:

- Операнд унарного оператора.

- По крайней мере один из операндов бинарного оператора.

- Либо операнд, либо тип возвращаемого значения оператора преобразования.

 Некоторые операторы имеют дополнительные ограничения по типам данных, как показано ниже.

- Если вы определяете операторы `IsTrue` и `IsFalse`, они должны возвращать тип `Boolean`.

- Если вы определяете операторы `<<` и `>>`, они должны указывать тип `Integer` для `operandtype` `operand2`.

Тип возвращаемого значения не должен соответствовать типу любого из операндов. Например, оператор сравнения, например `=` или `<>`, может возвращать `Boolean`, даже если ни один из операндов не `Boolean`.

## <a name="logical-and-bitwise-operators"></a>Логические и побитовые операторы

Операторы `And`, `Or`, `Not`и `Xor` могут выполнять логические или побитовые операции в Visual Basic. Однако при определении одного из этих операторов для класса или структуры можно определить только его побитовую операцию.

Оператор `AndAlso` нельзя определить непосредственно с помощью оператора `Operator`. Однако можно использовать `AndAlso`, если выполнены следующие условия.

- Вы определили `And` для тех же типов операндов, которые вы хотите использовать для `AndAlso`.

- Определение `And` возвращает тот же тип, что и класс или структура, в которой он определен.

- Вы определили оператор `IsFalse` в классе или структуре, для которой определены `And`.

Аналогичным образом можно использовать `OrElse`, если вы определили `Or` для одних и тех же операндов с типом возвращаемого значения класса или структуры и в классе или структуре определено `IsTrue`.

## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions

*Расширяющее преобразование* всегда выполняется успешно во время выполнения, в то время как *понижающие преобразования* могут завершиться ошибкой во время выполнения. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

При объявлении процедуры преобразования, которая будет `Widening`, код процедуры не должен создавать ошибок. Это подразумевает следующее:

- Он должен всегда возвращать допустимое значение типа `type`.

- Он должен поддерживать все возможные исключения и другие условия возникновения ошибок.

- Она должна поддерживать любые ошибки, возвращаемые из всех процедур, которые она вызывает.

Если существует вероятность того, что процедура преобразования может не быть выполнена или что она может вызвать необработанное исключение, необходимо объявить ее `Narrowing`.

## <a name="example"></a>Пример

В следующем примере кода используется оператор `Operator` для определения структуры, которая включает в себя процедуры оператора для `And`, `Or`, `IsFalse`и `IsTrue` операторов. `And` и `Or` принимают два операнда типа `abc` и тип возвращаемого значения `abc`. `IsFalse` и `IsTrue` принимают один операнд типа `abc` и возвращают `Boolean`. Эти определения позволяют вызывающему коду использовать `And`, `AndAlso`, `Or`и `OrElse` с операндами типа `abc`.

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a>См. также:

- [Оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Расширение](../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Практическое руководство. Вызов процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [Практическое руководство. Использование класса, в котором определяются операторы](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
