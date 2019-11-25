---
title: Оператор With...End With
ms.date: 07/20/2015
f1_keywords:
- vb.With
helpviewer_keywords:
- With keyword [Visual Basic]
- loop structures [Visual Basic], and With...End With statements
- execution [Visual Basic], on object
- instructions, repeating
- With...End With statements [Visual Basic]
- With statement [Visual Basic]
- With statement [Visual Basic], nesting
- objects [Visual Basic], accessing
- With block
- End keyword [Visual Basic], With...End With statements
ms.assetid: 340d5fbb-4f43-48ec-a024-80843c137817
ms.openlocfilehash: eb8790d0d8f82232a4b10e4e0e30165745c065c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352738"
---
# <a name="withend-with-statement-visual-basic"></a>Оператор With... End With (Visual Basic)

Выполняет последовательность операторов, которые многократно ссылаются на единственный объект или структуру, чтобы операторы могли использовать упрощенный синтаксис доступ к членам объекта или структуры.  При использовании структуры можно только считывать значения членов или вызвать методы. При попытке присвоения значений членам структуры, используемым в операторе `With...End With`, возникает ошибка.

## <a name="syntax"></a>Синтаксис

```vb
With objectExpression
    [ statements ]
End With
```

## <a name="parts"></a>Части

|Термин|Определение|
|---|---|
|`objectExpression`|Обязательный. Выражение, результатом которого является объект. Выражение может быть произвольно сложным и вычисляется только один раз. Результатом выражения могут быть данные любого типа, включая простейшие типы.|
|`statements`|Необязательный. Один или несколько операторов между `With` и `End With`, которые могут ссылаться на члены объекта, создаваемого при вычислении выражения `objectExpression`.|
|`End With`|Обязательный. Завершает определение блока `With`.|

## <a name="remarks"></a>Заметки

С помощью `With...End With` можно выполнять последовательность операторов с указанным объектом без необходимости многократного указания имени объекта. В блоке операторов `With` члены объекта можно указывать начиная с точки, как если бы перед ней стоял объект оператора `With`.

Например, чтобы изменить несколько свойств одного объекта, поместите операторы присваивания свойств внутрь блока `With...End With` и укажите объект лишь один раз, а не по одному разу для каждого свойства.

Если код обращается к одному и тому же объекту в нескольких операторах, оператор `With` обеспечивает следующие преимущества:

- Не требуется многократно вычислять сложное выражение или присваивать результат временной переменной, чтобы несколько раз сослаться на членов объекта.

- За счет исключения повторяющихся определяющих выражений код становится более понятным.

Тип данных у `objectExpression` может быть любым типом класса или структуры или даже простейшим типом Visual Basic (например `Integer`).  При результат вычисления выражения `objectExpression` не является объектом, можно только считывать значения его членов или вызвать методы. При попытке присвоения значений членам структуры, используемым в операторе `With...End With`, возникает ошибка.  Это та же самая ошибка, которая возникает, если сразу после вызова метода, возвращающего структуру, попытаться обратиться к члену результата функции и присвоить ему значение, например `GetAPoint().x = 1`.  Проблема в обоих случаях заключается в том, что структура существует только в стеке вызовов — в таких ситуациях не существует способа записи измененного члена структуры в некоторое расположение таким образом, чтобы весь остальной код программы мог видеть это изменение.

Выражение `objectExpression` вычисляется один раз при входе в блок. Переназначение выражения `objectExpression` изнутри блока `With` невозможно.

Внутри блока `With` к методам и свойствам только указанного объекта можно обращаться без их полного описания. Можно использовать методы и свойства других объектов, однако необходимо полностью указывать их имена.

Оператор `With...End With` можно разместить внутри другого такого оператора. Вложенные операторы `With...End With` могут быть сложны для понимания, если указываемые объекты не очевидны из контекста. Необходимо указывать полную ссылку на объект, находящийся во внешнем блоке `With`, при ссылке на него из внутреннего блока `With`.

Переходы внутрь блока операторов `With` из другой части программы запрещены.

Если блок не содержит цикла, операторы выполняются только один раз. Возможно вложение структур управления различных типов. For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).

> [!NOTE]
> Ключевое слово `With` можно также использовать в инициализаторах объектов. For more information and examples, see [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).
>
> Если блок `With` используется исключительно для инициализации свойств или полей только что созданного экземпляра объекта, рекомендуется использовать для этой цели инициализатор объекта.

## <a name="example"></a>Пример

В следующем примере в каждом блоке `With` выполняется несколько операторов для одного объекта.

[!code-vb[VbVbalrWithStatement#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#2)]

## <a name="example"></a>Пример

В следующем примере показаны вложенные операторы `With…End With`: Во вложенном операторе `With` этот синтаксис относится к внутреннему объекту.

[!code-vb[VbVbalrWithStatement#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic.List%601>
- [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
