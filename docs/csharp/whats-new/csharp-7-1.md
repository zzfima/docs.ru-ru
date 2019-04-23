---
title: Новые возможности C# 7.1
description: Обзор новых возможностей в C# 7.1.
ms.date: 04/09/2019
ms.openlocfilehash: c79c8576f9cbbd921ebf30bd84ee5a817d6dc6e7
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480967"
---
# <a name="whats-new-in-c-71"></a>Новые возможности C# 7.1

C# 7.1 — это первая доработанная версия для C#. Это означает, что новые выпуски для этого языка стали выходить чаще. Вы сможете использовать новые возможности раньше. В идеале — как только функция будет готова. В C# 7.1 можно настраивать компилятор в соответствии с указанной версией языка. Это позволяет отделить решение обновить средства от решения обновить версию языка.

В C# 7.1 добавлен элемент конфигурации [выбора версии языка](../language-reference/configure-language-version.md), три новые возможности языка и новое поведение компилятора.

Новые языковые функции в этом выпуске

* [`async` `Main` метод](#async-main)
  - Точка входа для приложения может иметь модификатор `async`.
* [`default` Литеральные выражения](#default-literal-expressions)
  - Литеральные выражения по умолчанию можно использовать в выражениях значения по умолчанию, если можно вывести тип целевого объекта.
* [Выводимые имена элементов кортежа](#inferred-tuple-element-names)
  - Имена элементов кортежа часто можно вывести из инициализации кортежа.
* [Сопоставление шаблонов в параметрах универсального типа](#pattern-matching-on-generic-type-parameters)
  - Выражения сопоставления шаблонов можно использовать с переменными, тип которых является параметром универсального типа.

Наконец, у компилятора есть два параметра `/refout` и `/refonly`, которые управляют [созданием базовой сборки](#reference-assembly-generation).

Чтобы использовать новые возможности доработанного выпуска, [настройте версию языка компилятора](../language-reference/configure-language-version.md), выбрав необходимую.

## <a name="async-main"></a>Async main

Метод *async main* позволяет использовать `await` в методе `Main`.
Раньше пришлось бы написать:

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

Теперь можно написать:

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

Если программа не возвращает код выхода, объявите метод `Main`, возвращающий <xref:System.Threading.Tasks.Task>:

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

См. подробнее в описании [async main](../programming-guide/main-and-command-args/index.md) в руководстве по программированию.

## <a name="default-literal-expressions"></a>Литеральные выражения по умолчанию

Литеральные выражения по умолчанию — это усовершенствование выражения значения по умолчанию.
Эти выражения инициализируют переменную до значения по умолчанию. Раньше пришлось бы написать:

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

Теперь можно опустить тип с правой стороны инициализации:

```csharp
Func<string, bool> whereClause = default;
```

См. подробнее об этом усовершенствовании в описании [выражений значений по умолчанию](../programming-guide/statements-expressions-operators/default-value-expressions.md) в руководстве по программированию на C#.

В этом усовершенствовании также изменены некоторые правила синтаксического анализа для [ключевого слова default](../language-reference/keywords/default.md).

## <a name="inferred-tuple-element-names"></a>Выводимые имена элементов кортежа

Эта возможность улучшает функцию кортежей, представленную в C# 7.0. Очень часто при инициализации кортежа переменные в правой части задания совпадают с именами для элементов кортежа:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

Имена элементов кортежа можно вывести из переменных, используемых для инициализации кортежа в C# 7.1:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

См. подробнее об этой функции в описании [кортежей](../tuples.md).

## <a name="pattern-matching-on-generic-type-parameters"></a>Сопоставление шаблонов в параметрах универсального типа

Начиная с версии C# 7.1, выражение шаблона для шаблона типа `is` и `switch` может быть типом параметра универсального типа. Эта возможность особенно полезна при проверке типов, которые могут представлять типы `struct` или `class`, когда вы хотите избежать упаковки-преобразования.

## <a name="reference-assembly-generation"></a>Создание базовой сборки

Существует два новых параметра компилятора, которые создают *сборки для справки*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) и [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).
В соответствующих статьях подробно рассматриваются эти параметры и базовые сборки.
