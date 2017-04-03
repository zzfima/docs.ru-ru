---
title: "Оператор lock (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
dev_langs:
- CSharp
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 020be199391789360ae9a25858bef54d8259ae56
ms.lasthandoff: 03/13/2017

---
# <a name="lock-statement-c-reference"></a>Оператор lock (Справочник по C#)
При помощи ключевого слова `lock` блок выражений можно пометить как важный фрагмент. Получив блокировку взаимного исключения для указанного объекта, выражения выполняются, а затем снимается блокировка. Следующий пример включает оператор `lock`.  
  
```  
  
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
  
 Дополнительные сведения см. в разделе [Синхронизация потоков](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4).  
  
## <a name="remarks"></a>Примечания  
 Ключевое слово `lock` не позволит одному потоку войти в важный раздел кода в тот момент, когда в нем находится другой поток. При попытке входа другого потока в заблокированный код потребуется дождаться снятия блокировки объекта.  
  
 Работа с потоками описана в разделе [Работа с потоками](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
 Ключевое слово `lock` вызывает <xref:System.Threading.Monitor.Enter%2A> в начале блока и <xref:System.Threading.Monitor.Exit%2A> в конце блока. <xref:System.Threading.ThreadInterruptedException> возникает, если <xref:System.Threading.Thread.Interrupt%2A> прерывает поток, который ожидает ввода в оператор `lock`.  
  
 Как правило, рекомендуется избегать блокировки типа `public` или экземпляров, которыми код не управляет. Это правило не соблюдается в распространенных конструкциях `lock (this)`, `lock (typeof (MyType))` и `lock ("myLock")`.  
  
-   `lock (this)` может привести к проблеме, если к экземпляру допускается открытый доступ.  
  
-   `lock (typeof (MyType))` может привести к проблеме, если к `MyType` допускается открытый доступ.  
  
-   `lock("myLock")` может привести к проблеме, поскольку любой код в процессе, использующий ту же строку, будет совместно использовать ту же блокировку.  
  
 Для блокировки рекомендуется использовать объект `private`. Если нужно защитить данные, являющиеся общими для всех экземпляров, рекомендуется использовать переменную объекта `private static`.  
  
 Нельзя использовать ключевое слово [await](../../../csharp/language-reference/keywords/await.md) в теле оператора `lock`.  
  
## <a name="example"></a>Пример  
 В следующем примере показано простое использование потоков без блокировки в C#.  
  
 [!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере используются потоки и ключевое слово`lock`. Так как присутствует оператор `lock`, блокировка оператора является важным разделом и `balance` никогда не будет отрицательным числом.  
  
 [!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Reflection.MethodImplAttributes>   
 <xref:System.Threading.Mutex>   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Работа с потоками](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/statement-keywords.md)   
 @System.Threading.Monitor   
 [Блокируемые операции](http://msdn.microsoft.com/library/cbda7114-c752-4f3e-ada1-b1e8dd262f2b)   
 [AutoResetEvent](http://msdn.microsoft.com/library/6d39c48d-6b37-4a9b-8631-f2924cfd9c18)   
 [Синхронизация потоков](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4)
