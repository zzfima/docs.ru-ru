---
title: Оператор lock (справочник по C#)
description: 'Ключевое слово lock используется при работе с потоками '
ms.date: 07/20/2015
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 6ed46837482642dfd7e1a96cd120fc18023c5e9f
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931197"
---
# <a name="lock-statement-c-reference"></a>Оператор lock (справочник по C#)

При помощи ключевого слова `lock` блок выражений можно пометить как важный фрагмент. Получив блокировку взаимного исключения для указанного объекта, выражения выполняются, а затем снимается блокировка. Следующий пример включает оператор `lock`.

```csharp
class Account
{
    decimal balance;
    private Object thisLock = new Object();

    public void Withdraw(decimal amount)
    {
        lock (thisLock)
        {
            if (amount > balance)
            {
                throw new Exception("Insufficient funds");
            }
            balance -= amount;
        }
    }
}
```

Дополнительные сведения см. в разделе [Синхронизация потоков](../../programming-guide/concepts/threading/thread-synchronization.md).

## <a name="remarks"></a>Примечания

Ключевое слово `lock` не позволит одному потоку войти в важный раздел кода в тот момент, когда в нем находится другой поток. При попытке входа другого потока в заблокированный код потребуется дождаться снятия блокировки объекта.

Работа с потоками описана в разделе [Работа с потоками](../../programming-guide/concepts/threading/index.md).

Ключевое слово `lock` вызывает <xref:System.Threading.Monitor.Enter%2A> в начале блока и <xref:System.Threading.Monitor.Exit%2A> в конце блока. Если <xref:System.Threading.Thread.Interrupt%2A> прерывает работу потока, который ожидает ввода оператора `lock`, возникает <xref:System.Threading.ThreadInterruptedException>.

Как правило, рекомендуется избегать блокировки типа `public` или экземпляров, которыми код не управляет. Это правило не соблюдается в распространенных конструкциях `lock (this)`, `lock (typeof (MyType))` и `lock ("myLock")`.

- `lock (this)` может привести к проблеме, если к экземпляру допускается открытый доступ.

- `lock (typeof (MyType))` может привести к проблеме, если к `MyType` допускается открытый доступ.

- `lock("myLock")` может привести к проблеме, поскольку любой код в процессе, использующий ту же строку, будет совместно использовать ту же блокировку.

Для блокировки рекомендуется использовать объект `private`. Если нужно защитить данные, являющиеся общими для всех экземпляров, рекомендуется использовать переменную объекта `private static`.

Нельзя использовать ключевое слово [await](await.md) в теле оператора `lock`.

## <a name="example---threads-without-locking"></a>Пример — потоки без блокировки

В следующем примере показано простое использование потоков без блокировки в C#:

[!code-csharp[csrefKeywordsFixedLock#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#5)]

## <a name="example---threads-using-locking"></a>Пример — потоки с блокировкой

В следующем примере используются потоки и ключевое слово`lock`. Так как присутствует оператор `lock`, блокировка оператора является важным разделом и `balance` никогда не будет отрицательным числом:

[!code-csharp[csrefKeywordsFixedLock#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#6)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- <xref:System.Reflection.MethodImplAttributes>
- <xref:System.Threading.Mutex>
- <xref:System.Threading.Monitor>
- [Справочник по C#](../../language-reference/index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Работа с потоками](../../programming-guide/concepts/threading/index.md)
- [Ключевые слова в C#](index.md)
- [Ключевые слова операторов](statement-keywords.md)
- [Блокируемые операции](../../../standard/threading/interlocked-operations.md)
- [AutoResetEvent](../../../standard/threading/autoresetevent.md)
- [Синхронизация потоков](../../programming-guide/concepts/threading/thread-synchronization.md)