---
title: Делегаты с именованными методами и Анонимные методы (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 6d7dcb3c7c6fa8f1d55237504c23cf468aa0e79d
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44274213"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a>Делегаты с именованными методами и Анонимные методы (Руководство по программированию в C#)
[Делегат](../../../csharp/language-reference/keywords/delegate.md) можно связать с именованным методом. При создании экземпляра делегата с использованием именованного метода этот метод передается в качестве параметра, например:  
  
 [!code-csharp[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]  
  
 Это называется использованием именованного метода. Делегаты, сконструированные с использованием именованного метода, могут инкапсулировать либо [статический](../../../csharp/language-reference/keywords/static.md) метод, либо метод экземпляра. Именованные методы являются единственным способом создать экземпляр делегата в ранних версиях C#. Тем не менее в ситуациях, когда создание нового метода нежелательно, C# позволяет создать экземпляр делегата напрямую, указав код блока, который делегат будет обрабатывать при его вызове. Этот блок может содержать лямбда-выражение или анонимный метод. Дополнительные сведения см. в разделе [Анонимные функции](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## <a name="remarks"></a>Примечания  
 Метод, который передается как параметр делегата, должен иметь такую же сигнатуру, что и объявление делегата.  
  
 Экземпляр делегата может инкапсулировать статический метод или метод экземпляра.  
  
 Несмотря на то, что делегат может использовать параметр [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), не рекомендуется делать это для делегатов многоадресных событий, поскольку в этом случае невозможно определить, какой делегат будет вызван.  
  
## <a name="example-1"></a>Пример 1  
 Ниже приведен простой пример объявления и использования делегата. Обратите внимание, что делегат `Del` и связанный с ним метод `MultiplyNumbers` имеют одинаковые сигнатуры.  
  
 [!code-csharp[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]  
  
## <a name="example-2"></a>Пример 2  
 В следующем примере делегат, сопоставленный одновременно со статическим методом и методом экземпляра, возвращает информацию из каждого из них.  
  
 [!code-csharp[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Делегаты](../../../csharp/programming-guide/delegates/index.md)  
- [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
- [Практическое руководство. Объединение делегатов (многоадресные делегаты)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
- [События](../../../csharp/programming-guide/events/index.md)
