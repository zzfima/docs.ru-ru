---
title: Оператор lock (справочник по C#)
description: Синхронизация доступа потоков к общему ресурсу с помощью оператора блокировки C#
ms.date: 10/01/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: cacc703e40f268c1dbca4174dc866ecae83cbd6c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125760"
---
# <a name="lock-statement-c-reference"></a>Оператор lock (справочник по C#)

Оператор `lock` получает взаимоисключающую блокировку заданного объекта перед выполнением определенных операторов, а затем снимает блокировку. Во время блокировки поток, удерживающий блокировку, может снова поставить и снять блокировку. Любой другой поток не может получить блокировку и ожидает ее снятия.

Оператор `lock` имеет форму

```csharp
lock (x)
{
    // Your code...
}
```

Здесь `x` — это выражение [ссылочного типа](reference-types.md). Оно является точным эквивалентом

```csharp
object __lockObj = x;
bool __lockWasTaken = false;
try
{
    System.Threading.Monitor.Enter(__lockObj, ref __lockWasTaken);
    // Your code...
}
finally
{
    if (__lockWasTaken) System.Threading.Monitor.Exit(__lockObj);
}
```

Так как в коде используется блок [try... finally](try-finally.md), блокировка освобождается, даже если возникает исключение в теле оператора `lock`.

Нельзя использовать ключевое слово [await](await.md) в теле оператора `lock`.

## <a name="remarks"></a>Примечания

При синхронизации доступа потоков к общему ресурсу блокируйте выделенный экземпляр объекта (например, `private readonly object balanceLock = new object();`) или другой экземпляр, который, скорее всего, не будет использоваться как объект блокировки другими частями кода. Не используйте один и тот же экземпляр объекта блокировки для разных общих ресурсов: это может привести к взаимоблокировке или состязанию при блокировке. В особенности избегайте использования следующих объектов в качестве объектов блокировки:

- `this`, так как он может использоваться вызывающими объектами как блокировка;
- экземпляров <xref:System.Type>, так как их может получать оператор [typeof](typeof.md) или отражение;
- строковых экземпляров, включая строковые литералы, так как они могут быть [интернированы](/dotnet/api/system.string.intern#remarks).

## <a name="example"></a>Пример

В следующем примере определяется класс `Account`, который синхронизирует доступ к закрытому полю `balance` путем блокировки выделенного экземпляра `balanceLock`. Использование того же экземпляра для блокировки гарантирует, что поле `balance` не смогут одновременно обновить два потока, пытающиеся вызвать методы `Debit` или `Credit` одновременно.

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Справочник по C#](../index.md)
- [Ключевые слова в C#](index.md)
- [Ключевые слова инструкций](statement-keywords.md)
- [Обзор примитивов синхронизации](../../../standard/threading/overview-of-synchronization-primitives.md)