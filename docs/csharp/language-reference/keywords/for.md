---
title: Оператор for (C#)
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: 5ebc478f8840173cacc0bc211061f3013379abd9
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422790"
---
# <a name="for-c-reference"></a>for (справочник по C#)

Оператор `for` выполняет оператор или блок операторов, пока определенное логическое выражение равно значению `true`.

В любой момент в блоке операторов `for` вы можете прервать цикл с помощью оператора [break](break.md) или перейти к следующей итерации в цикле с помощью оператора [continue](continue.md). Также можно выйти из цикла `for` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).

## <a name="structure-of-the-for-statement"></a>Структура оператора `for`

Оператор `for` определяет разделы *инициализатора*, *условия* и *итератора*:

```csharp
for (initializer; condition; iterator)
    body
```

Все три раздела добавляются по желанию. Тело цикла является оператором или блоком операторов.

В следующем примере показан оператор `for` со всеми определенными разделами:

[!code-csharp-interactive[for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a>Раздел *инициализатора*

Операторы в разделе *инициализатора* выполняются только один раз перед входом в цикл. Раздел *инициализатора* представляет собой один из следующих объектов:

- Объявление и инициализация локальной переменной цикла, к которой невозможно получить доступ вне цикла.

- Ноль или более выражений операторов из следующего списка, разделенные запятыми:

  - оператор [присваивания](../operators/assignment-operator.md)

  - вызов метода

  - префиксное или постфиксное выражение [приращения](../operators/arithmetic-operators.md#increment-operator-), такое как `++i` или `i++`

  - префиксное или постфиксное выражение [декремента](../operators/arithmetic-operators.md#decrement-operator---), такое как `--i` или `i--`

  - создание объекта с помощью оператора [new](../operators/new-operator.md)

  - выражение [await](../operators/await.md)

Раздел *инициализатора* в приведенном выше примере объявляет и инициализирует локальную переменную цикла `i`:

```csharp
int i = 0
```

### <a name="the-condition-section"></a>Раздел *условия*

Раздел *условия*, если он определен, должен быть логическим выражением. Это выражение оценивается перед каждой итерацией цикла. Если раздел *условия* отсутствует или логическое выражение имеет значение `true`, выполняется следующая итерация цикла. В противном случае выполняется выход из цикла.

Раздел *условия* в приведенном выше примере определяет, завершится ли цикл в зависимости от значения локальной переменной цикла:

```csharp
i < 5
```

### <a name="the-iterator-section"></a>Раздел *итератора*

Раздел *итератора* определяет, что происходит после каждой итерации тела цикла. Раздел *итератора* содержит ноль или более следующих выражений оператора, разделенных запятыми:

- оператор [присваивания](../operators/assignment-operator.md)

- вызов метода

- префиксное или постфиксное выражение [приращения](../operators/arithmetic-operators.md#increment-operator-), такое как `++i` или `i++`

- префиксное или постфиксное выражение [декремента](../operators/arithmetic-operators.md#decrement-operator---), такое как `--i` или `i--`

- создание объекта с помощью оператора [new](../operators/new-operator.md)

- выражение [await](../operators/await.md)

Раздел *итератора* в приведенном выше примере увеличивает локальную переменную цикла:

```csharp
i++
```

## <a name="examples"></a>Примеры

В следующем примере показано несколько менее распространенных вариантов использования разделов оператора `for`: присваивание значения внешней переменной цикла в разделе *инициализатора*, вызов метода в разделах *инициализатора* и *итератора* и изменение значения двух переменных в разделе *итератора*. Нажмите **Запустить** для выполнения примера кода. После этого можно изменить код и запустить его еще раз.

[!code-csharp-interactive[not typical for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#6)]

В следующем примере определен бесконечный цикл `for`:

[!code-csharp[infinite for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#7)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор for](~/_csharplang/spec/statements.md#the-for-statement) в документации [Предварительная спецификация C# 6.0](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [foreach, in](foreach-in.md)
