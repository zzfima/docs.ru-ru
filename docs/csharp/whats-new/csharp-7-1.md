---
title: Новые возможности C# 7.1
description: Обзор новых возможностей в C# 7.1.
ms.date: 08/16/2017
ms.openlocfilehash: 565db102284424f9d8f6fa04ec9c74b52c9da0e6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728658"
---
# <a name="whats-new-in-c-71"></a>Новые возможности C# 7.1

C# 7.1 — это первая доработанная версия для C#. Это означает, что новые выпуски для этого языка стали выходить чаще. Вы сможете использовать новые возможности раньше. В идеале — как только функция будет готова. В C# 7.1 можно настраивать компилятор в соответствии с указанной версией языка. Это позволяет отделить решение обновить средства от решения обновить версию языка.

В C# 7.1 добавлен элемент конфигурации [выбора версии языка](../language-reference/configure-language-version.md), три новые возможности языка и новое поведение компилятора.

Новые языковые функции в этом выпуске

* [`async` метод `Main`](#async-main)
  - Точка входа для приложения может иметь модификатор `async`.
* [Литеральные выражения `default`](#default-literal-expressions)
  - Литеральные выражения по умолчанию можно использовать в выражениях значения по умолчанию, если можно вывести тип целевого объекта.
* [Выводимые имена элементов кортежа](#inferred-tuple-element-names)
  - Имена элементов кортежа часто можно вывести из инициализации кортежа.

Наконец, у компилятора есть два параметра `/refout` и `/refonly`, которые управляют [созданием базовой сборки](#reference-assembly-generation).

Чтобы использовать новые возможности доработанной версии, [настройте версию языка компилятора](../language-reference/configure-language-version.md) и выберите версию.

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

Дополнительные сведения см. в разделе [async main](../programming-guide/main-and-command-args/index.md) в руководстве по программированию.

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

Дополнительные сведения об этом усовершенствовании см. в разделе о [выражениях значения по умолчанию](../programming-guide/statements-expressions-operators/default-value-expressions.md) в руководстве по программированию на C#.

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

Дополнительные сведения об этой функции см. в разделе [Кортежи](../tuples.md).

## <a name="reference-assembly-generation"></a>Создание базовой сборки

Существует два новых параметра компилятора, которые создают *сборки для справки*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) и [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).
В соответствующих разделах подробно рассматриваются эти параметры и базовые сборки.
