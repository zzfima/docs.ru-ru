---
title: "Делегаты с именованными методами и делегаты с анонимными методами (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "делегаты [C#], сравнение именованных методов с анонимными"
  - "методы [C#], в делегатах"
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Делегаты с именованными методами и делегаты с анонимными методами (Руководство по программированию в C#)
[Делегат](../../../csharp/language-reference/keywords/delegate.md) может быть назначен именованному методу.  При создании экземпляра делегата с помощью именованного метода этот метод передается в качестве параметра, например:  
  
 [!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#1)]  
  
 Это называется использованием именованного метода.  Делегаты, созданные с помощью именованного метода, могут инкапсулировать [статический](../../../csharp/language-reference/keywords/static.md) метод или метод экземпляра.  Именованные методы являются единственным способом создания экземпляра делегата в ранних версиях C\#.  Однако в ситуациях, когда создание нового метода является нежелательным, C\# позволяет создать экземпляр делегата и сразу же указать блок кода, обрабатываемый делегатом при вызове.  Блок может содержать либо лямбда\-выражение, либо анонимный метод.  Дополнительные сведения см. в разделе [Анонимные функции](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## Заметки  
 Метод, который передается как параметр делегата, должен иметь такую же сигнатуру, как и объявление делегата.  
  
 Экземпляр делегата может инкапсулировать статический метод или метод экземпляра.  
  
 Хотя делегат может использовать параметр [out](../../../csharp/language-reference/keywords/out.md), с делегатами групповых событий его использование не рекомендуется, так как при этом нельзя определить, какой делегат будет вызван.  
  
## Пример 1  
 Ниже приведен простой пример объявления и использования делегата.  Обратите внимание на то, что как делегат `Del`, так и сопоставленный метод `MultiplyNumbers` имеют одинаковую сигнатуру  
  
 [!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#2)]  
  
## Пример 2  
 В следующем примере один делегат сопоставлен как со статическим методом, так и с методом экземпляра и возвращает из каждого метода определенные сведения.  
  
 [!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#3)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)   
 [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)   
 [Практическое руководство. Объединение делегатов \(многоадресные делегаты\)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)   
 [События](../../../csharp/programming-guide/events/index.md)