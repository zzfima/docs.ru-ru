---
title: "Упорядочение результатов предложения соединения"
description: "Упорядочение результатов предложения соединения."
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0252dd62e5638ffd1ab4eeebcfc2382a65997e30
ms.lasthandoff: 03/13/2017

---
# <a name="order-the-results-of-a-join-clause"></a>Упорядочение результатов предложения соединения
В этом примере показано, как упорядочить результаты операции соединения. Обратите внимание на то, что упорядочение выполняется после соединения. Несмотря на то, что предложение `orderby` с одним или несколькими исходными последовательностями использовать до соединения можно, обычно это не рекомендуется. Некоторые поставщики LINQ могут не сохранять этот порядок после соединения.  
  
## <a name="example"></a>Пример  
 Этот запрос создает группу соединения, а затем сортирует группы по элементу категории, который остается в области действия. В инициализаторе анонимного типа подзапрос упорядочивает все соответствующие элементы из последовательности продуктов.  
  
 [!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a>См. также  
 [Выражения запросов LINQ](index.md)   
 [предложение orderby](../language-reference/keywords/orderby-clause.md)   
 [предложение join](../language-reference/keywords/join-clause.md) 
