---
title: Делегаты с именованными методами и Руководство по программированию на C#. Анонимные методы
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 1ec366999ca6457471b705fa83f06fcde4293f4e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712381"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a>Делегаты с именованными методами и Анонимные методы (Руководство по программированию в C#)
[Делегат](../../language-reference/builtin-types/reference-types.md) можно связать с именованным методом. При создании экземпляра делегата с использованием именованного метода этот метод передается в качестве параметра, например:  
  
 [!code-csharp[csProgGuideDelegates#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#1)]  
  
 Это называется использованием именованного метода. Делегаты, сконструированные с использованием именованного метода, могут инкапсулировать либо [статический](../../language-reference/keywords/static.md) метод, либо метод экземпляра. Именованные методы являются единственным способом создать экземпляр делегата в ранних версиях C#. Тем не менее в ситуациях, когда создание нового метода нежелательно, C# позволяет создать экземпляр делегата напрямую, указав код блока, который делегат будет обрабатывать при его вызове. Этот блок может содержать лямбда-выражение или анонимный метод. Дополнительные сведения см. в разделе [Анонимные функции](../statements-expressions-operators/anonymous-functions.md).  
  
## <a name="remarks"></a>Примечания  
 Метод, который передается как параметр делегата, должен иметь такую же сигнатуру, что и объявление делегата.  
  
 Экземпляр делегата может инкапсулировать статический метод или метод экземпляра.  
  
 Несмотря на то, что делегат может использовать параметр [out](../../language-reference/keywords/out-parameter-modifier.md), не рекомендуется делать это для делегатов многоадресных событий, поскольку в этом случае невозможно определить, какой делегат будет вызван.  
  
## <a name="example-1"></a>Пример 1  
 Ниже приведен простой пример объявления и использования делегата. Обратите внимание, что делегат `Del` и связанный с ним метод `MultiplyNumbers` имеют одинаковые сигнатуры.  
  
 [!code-csharp[csProgGuideDelegates#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#2)]  
  
## <a name="example-2"></a>Пример 2  
 В следующем примере делегат, сопоставленный одновременно со статическим методом и методом экземпляра, возвращает информацию из каждого из них.  
  
 [!code-csharp[csProgGuideDelegates#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#3)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Делегаты](./index.md)
- [Практическое руководство. Объединение делегатов (многоадресные делегаты)](./how-to-combine-delegates-multicast-delegates.md)
- [События](../events/index.md)
