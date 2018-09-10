---
title: Упорядочение результатов предложения соединения (LINQ в C#)
description: Узнайте, как упорядочивать результаты предложения соединения LINQ в C#.
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: 13cd6cb202cf67def17310db6d98e368ce837646
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516990"
---
# <a name="order-the-results-of-a-join-clause"></a>Упорядочение результатов предложения соединения

В этом примере показано, как упорядочить результаты операции соединения. Обратите внимание на то, что упорядочение выполняется после соединения. Несмотря на то, что предложение `orderby` с одним или несколькими исходными последовательностями использовать до соединения можно, обычно это не рекомендуется. Некоторые поставщики LINQ могут не сохранять этот порядок после соединения.

## <a name="example"></a>Пример

Этот запрос создает группу соединения, а затем сортирует группы по элементу категории, который остается в области действия. В инициализаторе анонимного типа подзапрос упорядочивает все соответствующие элементы из последовательности продуктов.

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a>См. также

- [LINQ](index.md)  
- [предложение orderby](../language-reference/keywords/orderby-clause.md)  
- [предложение join](../language-reference/keywords/join-clause.md)  