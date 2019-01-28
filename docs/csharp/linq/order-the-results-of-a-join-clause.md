---
title: Упорядочение результатов предложения соединения (LINQ в C#)
description: Узнайте, как упорядочивать результаты предложения соединения LINQ в C#.
ms.date: 12/01/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f60000b83bf378dd8740b7255d421dd4335614c4
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857892"
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
