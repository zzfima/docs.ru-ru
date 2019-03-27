---
title: Справочник по C#. Условные операции со значением "null"
ms.custom: seodec18
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 9cbf8a0f860f0bc0328cd98e558b20b5e8e1bf8f
ms.sourcegitcommit: 344d82456f27d09a210671214a14cfd7daf1f97c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2019
ms.locfileid: "58348847"
---
# <a name="-and--null-conditional-operators-c-reference"></a>?. и ?[]: операторы проверки на NULL (справочник по C#)

Проверяет значение левого операнда на наличие значения NULL перед выполнением операции доступа к элементу (`?.`) или индексу (`?[]`). Возвращает `null`, если левый операнд имеет значение `null`.

Эти операторы позволяют писать меньше кода для проверок значений null, особенно если речь идет о внедрении в структуры данных.

```csharp
int? length = customers?.Length; // null if customers is null
Customer first = customers?[0];  // null if customers is null
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null
```

Операторы с условием NULL предусматривают сокращенную обработку.  Если одна из операций в цепочке условных операций доступа к члену и операций индексирования возвращает значение NULL, то выполнение остальной части цепочки прекращается.  В приведенном ниже примере `E` не выполняется, если `A`, `B` или `C` имеет значение NULL.

```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

Другим примером использования для доступа к элементам с условием NULL является вызов делегатов в потокобезопасном режиме с существенно меньшим объемом кода.  Для старого способа требуется примерно следующий код:

```csharp
var handler = this.PropertyChanged;
if (handler != null)
    handler(…);
```

Новый способ гораздо проще:

```csharp
PropertyChanged?.Invoke(…)
```

Новый способ является потокобезопасным, так как компилятор создает код для вычисления `PropertyChanged` только один раз, запоминая результат во временной переменной. Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `PropertyChanged?(e)` для вызова делегатов с условием NULL.

## <a name="language-specifications"></a>Спецификации языков

Дополнительные сведения см. в разделе об [операторах с условием NULL](~/_csharplang/spec/expressions.md#null-conditional-operator) в [Спецификации языка C#](../language-specification/index.md). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.

## <a name="see-also"></a>См. также

- [Оператор ?? (оператор объединения со значением NULL)](null-coalescing-operator.md)
- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)