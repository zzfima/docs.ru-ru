---
title: out (универсальный модификатор)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
ms.openlocfilehash: 0460015b44971fa638dba47183690ffcc89ca55f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351427"
---
# <a name="out-generic-modifier-visual-basic"></a>Out (универсальный модификатор) (Visual Basic)

For generic type parameters, the `Out` keyword specifies that the type is covariant.

## <a name="remarks"></a>Заметки

Ковариация позволяет использовать производные типы со степенью наследования больше, нежели у типа, заданного универсальным параметром. Благодаря этому можно осуществлять неявное преобразование классов, реализующих вариантные интерфейсы, и неявное преобразование типов делегатов.

Дополнительные сведения см. в разделе [Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md).

## <a name="rules"></a>Правила

Ключевое слово `Out` может применяться в универсальных интерфейсах и делегатах.

В универсальном интерфейсе параметр типа может быть объявлен ковариантным, если он удовлетворяет следующим условиям:

- Параметр типа используется только в качестве типа значения, возвращаемого методами интерфейса, и не используется в качестве типа аргументов метода.

    > [!NOTE]
    > Существует одно исключение из данного правила. Если в ковариантном интерфейсе в качестве параметра метода используется контравариантный универсальный делегат, ковариантный тип можно использовать в качестве параметра универсального типа для этого делегата. Дополнительные сведения о ковариантных и контравариантных универсальных методах-делегатах см. в разделе [Вариативность в делегатах](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) и [Использование вариативности в универсальных методах-делегатах Func и Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

- Параметр типа не используется в качестве универсального ограничения для методов интерфейса.

In a generic delegate, a type parameter can be declared covariant if it is used only as a method return type and not used for method arguments.

Ковариация и контравариантность поддерживаются для ссылочных типов, но не для типов значений.

In Visual Basic, you cannot declare events in covariant interfaces without specifying the delegate type. Also, covariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.

## <a name="behavior"></a>Поведение

Интерфейс с параметром ковариантного типа позволяет своим методам возвращать аргументы производных типов, степень наследования у которых больше, чем у параметра типа. Например, так как в .NET Framework 4 в <xref:System.Collections.Generic.IEnumerable%601> тип T является ковариантным, можно назначить объект типа `IEnumerable(Of String)` объекту типа `IEnumerable(Of Object)` без применения каких-либо специальных методов преобразования.

Ковариантный делегат может быть назначен другому делегату того же типа, но с производным параметром универсального типа большей степени.

## <a name="example"></a>Пример

В следующем примере показано, как объявить, расширить и реализовать ковариантный универсальный интерфейс. В нем также показано, как использовать неявное преобразование для классов, реализующих ковариантный интерфейс.

[!code-vb[vbVarianceKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#3)]

## <a name="example"></a>Пример

В следующем примере кода показано, как объявить ковариантный универсальный метод-делегат. It also shows how you can use implicit conversion for delegate types.

[!code-vb[vbVarianceKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#4)]

## <a name="see-also"></a>См. также

- [Расхождение в универсальных интерфейсах](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
