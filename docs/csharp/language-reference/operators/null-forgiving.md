---
title: '! — оператор (допускающий значение NULL) — справочник по C#'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 865e55a28e2f3db85d50a81f6ab29c354ee3c62a
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319096"
---
# <a name="-null-forgiving-operator-c-reference"></a>! — оператор (допускающий значение NULL) (справочник по C#)

Унарный постфиксный оператор `!`, доступный в C# 8.0 и более поздних версиях, допускает значение NULL. При включенном [контексте аннотаций, допускающем значение NULL](../../nullable-references.md#nullable-annotation-context) вы используете оператор, опускающий NULL, для объявления того, что выражение `x` для ссылочного типа, допускающего значение NULL, не равно нулю: `x!`. Унарный префиксный оператор `!` является [оператором логического отрицания](boolean-logical-operators.md#logical-negation-operator-).

Оператор, допускающий NULL, ни на что не влияет во время выполнения. Он влияет только на статический анализ потока компилятора путем изменения состояния NULL выражения. Во время выполнения выражение `x!` сравнивается с результатом базового выражения `x`.

Дополнительные сведения о ссылочных типах, допускающих значения NULL, см. в разделе [Ссылочные типы, допускающие значение NULL](../../nullable-references.md).

## <a name="examples"></a>Примеры

Один из вариантов использования оператора, допускающего значение NULL, — тестирование логики проверки аргументов. Например, рассмотрим следующий класс.

[!code-csharp[Person class](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#PersonClass)]

С помощью [платформы тестирования MSTest](../../../core/testing/unit-testing-with-mstest.md) можно создать следующий тест для логики проверки в конструкторе:

[!code-csharp[Person test](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#TestPerson)]

Без оператора, допускающего значение NULL, компилятор создает следующее предупреждение для предыдущего кода: `Warning CS8625: Cannot convert null literal to non-nullable reference type`. Используя оператор, допускающий значение NULL, вы позволяете компилятору узнать, что передача `null` ожидается, и о ней не нужно предупреждать.

Можно также использовать оператор, допускающий значение NULL, если вы точно знаете, что выражение не может быть `null`, но компилятор не распознает это. В следующем примере, если метод `IsValid` возвращает `true`, его аргумент не является `null`, и вы можете безопасно отменить его ссылку:

[!code-csharp[Use null-forgiving operator](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseNullForgiving)]

Без оператора, допускающего значение NULL, компилятор создает следующее предупреждение для кода `p.Name`: `Warning CS8602: Dereference of a possibly null reference`.

Если вы можете изменить метод `IsValid`, можно использовать атрибут [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute), чтобы сообщить компилятору, что аргумент метода `IsValid` не может быть `null`, когда метод возвращает `true`:

[!code-csharp[Use an attribute](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseAttribute)]

В предыдущем примере не нужно использовать оператор, допускающий значение NULL, поскольку компилятор содержит достаточно информации, чтобы определить, что `p` не может быть `null` внутри `if`. Дополнительные сведения об атрибутах, позволяющих указать дополнительные сведения о состоянии NULL для переменной, см. в разделе [Дополнение API атрибутами для определения ожидаемых значений NULL](../../nullable-attributes.md).

## <a name="c-language-specification"></a>Спецификация языка C#

См. сведения об [операторе, допускающем значение NULL](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator), в [черновике спецификации по ссылочным типам допускающим значение NULL](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Учебник. Разработка с использованием ссылочных типов, допускающих значение NULL](../../tutorials/nullable-reference-types.md)
