---
title: Предложение orderby. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: fc6e47270c4ae035a6387bf0e8d29efcd42e902f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240987"
---
# <a name="orderby-clause-c-reference"></a>Предложение orderby (Справочник по C#)

В выражении запроса предложение `orderby` задает сортировку возвращаемой последовательности или вложенной последовательности (группы) в порядке возрастания или убывания. Для выполнения одной или нескольких операций последующей сортировки можно указать несколько ключей. Сортировка выполняется с помощью функции сравнения по умолчанию для соответствующего типа элемента. По умолчанию используется порядок сортировки по возрастанию. Также можно указать настраиваемую функцию сравнения. Тем не менее сделать это можно только с использованием синтаксиса на основе метода. Дополнительные сведения см. в разделе [Сортировка данных](../../programming-guide/concepts/linq/sorting-data.md).

## <a name="example"></a>Пример

В следующем примере первый запрос сортирует слова в алфавитном порядке, начиная с A. Второй запрос сортирует эти же слова в порядке убывания. (Ключевое слово `ascending` определяет порядок сортировки по умолчанию и может быть опущено.)

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a>Пример

В следующем примере выполняется первичная сортировка списка студентов по фамилиям, а затем дополнительная сортировка по именам.

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a>Примечания

Во время компиляции предложение `orderby` преобразуется в вызов метода <xref:System.Linq.Enumerable.OrderBy%2A>. Если в предложении `orderby` используется несколько ключей, они преобразуются в вызовы метода <xref:System.Linq.Enumerable.ThenBy%2A>.

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Ключевые слова запроса (LINQ)](query-keywords.md)
- [LINQ](../../linq/index.md)
- [предложение group](group-clause.md)
- [Приступая к работе с LINQ в C#](../../programming-guide/concepts/linq/getting-started-with-linq.md)