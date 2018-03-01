---
title: "Оператор lock (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eb48c2b1554ad2817406eaef42b4cb336ea46862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lock-statement-c-reference"></a>Оператор lock (Справочник по C#)
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
  
-   `lock (this)` может привести к проблеме, если к экземпляру допускается открытый доступ.  
  
-   `lock (typeof (MyType))` может привести к проблеме, если к `MyType` допускается открытый доступ.  
  
-   `lock("myLock")` может привести к проблеме, поскольку любой код в процессе, использующий ту же строку, будет совместно использовать ту же блокировку.  
  
 Для блокировки рекомендуется использовать объект `private`. Если нужно защитить данные, являющиеся общими для всех экземпляров, рекомендуется использовать переменную объекта `private static`.  
  
 Нельзя использовать ключевое слово [await](../../../csharp/language-reference/keywords/await.md) в теле оператора `lock`.  
  
## <a name="example"></a>Пример  
 В следующем примере показано простое использование потоков без блокировки в C#.  
  
 [!code-csharp[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере используются потоки и ключевое слово`lock`. Так как присутствует оператор `lock`, блокировка оператора является важным разделом и `balance` никогда не будет отрицательным числом.  
  
 [!code-csharp[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Reflection.MethodImplAttributes>  
 <xref:System.Threading.Mutex>  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Работа с потоками](../../programming-guide/concepts/threading/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/statement-keywords.md)  
 <xref:System.Threading.Monitor>  
 [Блокируемые операции](../../../standard/threading/interlocked-operations.md)  
 [AutoResetEvent](../../../standard/threading/autoresetevent.md)  
 [Синхронизация потоков](../../programming-guide/concepts/threading/thread-synchronization.md)
