---
title: Оператор lock (справочник по C#)
description: Использование выражения блокировки C# для синхронизации доступа потоков к общему ресурсу
ms.date: 08/28/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 2b6fbfb2f81d7745c4effb9ea0087f34cc872a6c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858360"
---
# <a name="lock-statement-c-reference"></a>Оператор lock (справочник по C#)

Оператор `lock` создает взаимоисключающую блокировку заданного объекта перед выполнением определенных операторов, а затем снимает блокировку. Во время блокировки поток, удерживающий блокировку, может снова получить и снять блокировку. Любой другой поток не может получить блокировку и ожидает ее снятия.

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

При синхронизации доступа потоков к общему ресурсу блокируйте выделенный экземпляр объекта (например, `private readonly object balanceLock = new object();`) или другой экземпляр, который, скорее всего, не будет использоваться как объект блокировки другими частями кода. Не используйте один и тот же экземпляр объекта блокировки для разных общих ресурсов: это может привести к взаимоблокировке или состязанию при блокировке. В частности, старайтесь не использовать:

- `this` (может использоваться вызывающими объектами как блокировка);
- экземпляры <xref:System.Type> (может получатся оператором [typeof](typeof.md) или отражением);
- строковые экземпляры, включая строковые литералы,

как объекты блокировки.

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
- [Ключевые слова операторов](statement-keywords.md)
- [Блокируемые операции](../../../standard/threading/interlocked-operations.md)
- [Обзор примитивов синхронизации](../../../standard/threading/overview-of-synchronization-primitives.md)