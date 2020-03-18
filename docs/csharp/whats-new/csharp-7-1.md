---
title: Новые возможности C# 7.1
description: Обзор новых возможностей в C# 7.1.
ms.date: 04/09/2019
ms.openlocfilehash: 5d2d6f51b6422f5b4db5c6bd275b5ffce1f695f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398355"
---
# <a name="whats-new-in-c-71"></a>Новые возможности C# 7.1

C# 7.1 — это первая доработанная версия для C#. Это означает, что новые выпуски для этого языка стали выходить чаще. Вы сможете использовать новые возможности раньше. В идеале — как только функция будет готова. В C# 7.1 можно настраивать компилятор в соответствии с указанной версией языка. Это позволяет отделить решение обновить средства от решения обновить версию языка.

В C# 7.1 добавлен элемент конфигурации [выбора версии языка](../language-reference/configure-language-version.md), три новые возможности языка и новое поведение компилятора.

Новые языковые функции в этом выпуске

- [Метод `async` `Main`](#async-main)
  - Точка входа для приложения может иметь модификатор `async`.
- [Литеральные выражения `default`](#default-literal-expressions)
  - Литеральные выражения по умолчанию можно использовать в выражениях значения по умолчанию, если можно вывести тип целевого объекта.
- [Выводимые имена элементов кортежа](#inferred-tuple-element-names)
  - Имена элементов кортежа часто можно вывести из инициализации кортежа.
- [Сопоставление шаблонов в параметрах универсального типа](#pattern-matching-on-generic-type-parameters)
  - Выражения сопоставления шаблонов можно использовать с переменными, тип которых является параметром универсального типа.

Наконец, у компилятора есть два параметра `-refout` и `-refonly`, которые управляют [созданием базовой сборки](#reference-assembly-generation).

Чтобы использовать новые возможности доработанной версии, [настройте версию языка компилятора](../language-reference/configure-language-version.md) и выберите версию.

В оставшейся части этой статьи представлены общие сведения об этих функциях. Каждая функция сопровождается обоснованием. Вы изучите синтаксис Эти функции можно изучить в своей среде с помощью глобального средства `dotnet try`:

1. Установите глобальное средство [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).
1. Клонируйте репозиторий [dotnet/try-samples](https://github.com/dotnet/try-samples).
1. Для репозитория *try-samples* установите в качестве текущего каталога подкаталог *csharp7*.
1. Выполните `dotnet try`.

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

Дополнительные сведения см. в разделе [о литерале default](../language-reference/operators/default.md#default-literal) в статье об [операторе default](../language-reference/operators/default.md).

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

Существует два новых параметра компилятора, которые создают *только базовые сборки*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) и [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).
В соответствующих статьях подробно рассматриваются эти параметры и базовые сборки.
