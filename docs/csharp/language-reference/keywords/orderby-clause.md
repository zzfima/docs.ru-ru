---
title: "Предложение orderby (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- orderby
- orderby_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ec9507e4c1d9691d90d47cdbb20fdb22fc281d24
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="orderby-clause-c-reference"></a>Предложение orderby (Справочник по C#)
В выражении запроса предложение `orderby` задает сортировку возвращаемой последовательности или вложенной последовательности (группы) в порядке возрастания или убывания. Для выполнения одной или нескольких операций последующей сортировки можно указать несколько ключей. Сортировка выполняется с помощью функции сравнения по умолчанию для соответствующего типа элемента. По умолчанию используется порядок сортировки по возрастанию. Также можно указать настраиваемую функцию сравнения. Тем не менее сделать это можно только с использованием синтаксиса на основе метода. Дополнительные сведения см. в разделе [Сортировка данных](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48).  
  
## <a name="example"></a>Пример  
 В следующем примере первый запрос сортирует слова в алфавитном порядке, начиная с A. Второй запрос сортирует эти же слова в порядке убывания. (Ключевое слово `ascending` определяет порядок сортировки по умолчанию и может быть опущено.)  
  
 [!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется первичная сортировка списка студентов по фамилиям, а затем дополнительная сортировка по именам.  
  
 [!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]  
  
## <a name="remarks"></a>Примечания  
 Во время компиляции предложение `orderby` преобразуется в вызов метода <xref:System.Linq.Enumerable.OrderBy%2A>. Если в предложении `orderby` используется несколько ключей, они преобразуются в вызовы метода <xref:System.Linq.Enumerable.ThenBy%2A>.  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Ключевые слова запроса (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Предложение group](../../../csharp/language-reference/keywords/group-clause.md)   
 [Приступая к работе с LINQ в C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

