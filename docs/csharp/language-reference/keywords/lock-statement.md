---
title: "Оператор lock (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "lock_CSharpKeyword"
  - "lock"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lock - ключевое слово [C#]"
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 43
---
# Оператор lock (Справочник по C#)
При помощи ключевого слова `lock` блок операторов можно пометить как важный фрагмент, получив блокировку взаимного исключения для указанного объекта, выполнив оператор, а затем сняв блокировку.  Следующий пример включает `lock` формулировку.  
  
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
  
 Дополнительные сведения см. в разделе [Синхронизация потоков](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Заметки  
 Ключевое слово `lock` не позволит одному потоку войти в важный раздел кода в тот момент, когда в нем находится другой поток.  При попытке входа другого потока в заблокированный код потребуется дождаться снятия блокировки объекта.  
  
 Работа с потоками описана в разделе [Потоки](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Ключевое слово `lock` вызывает <xref:System.Threading.Monitor.Enter%2A> в начале блока и <xref:System.Threading.Monitor.Exit%2A> в конце блока.  <xref:System.Threading.ThreadInterruptedException> возникает, если <xref:System.Threading.Thread.Interrupt%2A> прерывает поток, который ожидает входа в выписку `lock`.  
  
 Как правило, рекомендуется избегать блокировки типа `public` или экземпляров, которыми код не управляет.  Распространенные конструкторы `lock (this)`, `lock (typeof (MyType))` и `lock ("myLock")` не соблюдают это правило.  
  
-   `lock (this)` может привести к проблеме, если к экземпляру допускается открытый доступ.  
  
-   `lock (typeof (MyType))` может привести к проблеме, если к `MyType` допускается открытый доступ.  
  
-   `lock("myLock")` может привести к проблеме, поскольку любой код в процессе, используя ту же строку, будет совместно использовать ту же блокировку.  
  
 Для блокировки рекомендуется определять объект `private` или переменную объекта `private static`, чтобы защитить данные, являющиеся общими для всех экземпляров.  
  
 Нельзя использовать ключевое слово [подождите](../../../csharp/language-reference/keywords/await.md) в теле выписки `lock`.  
  
## Пример  
 В следующем примере показано простое использование потоков без блокировки в C\#.  
  
 [!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefFixedLock/csrefKeywordsFixedLock.cs#5)]  
  
## Пример  
 В следующем примере используются потоки и ключевое слово `lock`.  Так как присутствует оператор `lock`, блокировка оператора является важным разделом и `balance` никогда не будет отрицательным числом.  
  
 [!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefFixedLock/csrefKeywordsFixedLock.cs#6)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 <xref:System.Reflection.MethodImplAttributes>   
 <xref:System.Threading.Mutex>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Потоки](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/statement-keywords.md)   
 [Мониторы](../Topic/Monitors.md)   
 [Interlocked Operations](../Topic/Interlocked%20Operations.md)   
 [AutoResetEvent](../Topic/AutoResetEvent.md)   
 [Синхронизация потоков](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md)