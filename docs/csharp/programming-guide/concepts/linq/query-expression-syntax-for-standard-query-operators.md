---
title: Синтаксис выражений запроса для стандартных операторов запроса (C#)
ms.date: 07/20/2015
ms.assetid: e1e17ef2-68ff-4c26-b6e2-015668227fa5
ms.openlocfilehash: dac63ae165b88924cb0e91336571173f764569ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591426"
---
# <a name="query-expression-syntax-for-standard-query-operators-c"></a>Синтаксис выражений запроса для стандартных операторов запроса (C#)
Некоторые из наиболее часто используемых стандартных операторов запросов имеют представление в виде ключевых слов в синтаксисе языка C#, что позволяет вызывать их как часть *выражения запроса*. Выражение запроса является более удобочитаемой формой задания запроса, чем его *основанный на методах* эквивалент. Предложения выражений запросов преобразуются в вызовы методов запросов во время компиляции.  
  
## <a name="query-expression-syntax-table"></a>Таблица синтаксиса выражений запросов  
 В следующей таблице приводится список стандартных операторов запросов, имеющих эквивалентные предложения выражений запросов.  
  
|Метод|Синтаксис выражения запроса C#|  
|------------|---------------------------------|  
|<xref:System.Linq.Enumerable.Cast%2A>|Использование явным образом типизированной переменной диапазона, например:<br /><br /> `from int i in numbers`<br /><br /> (Дополнительные сведения см. в разделе [Предложение from](../../../language-reference/keywords/from-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`group … by`<br /><br /> -или-<br /><br /> `group … by … into …`<br /><br /> (Дополнительные сведения см. в разделе [Предложение group](../../../language-reference/keywords/group-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`join … in … on … equals … into …`<br /><br /> (Дополнительные сведения см. в разделе [Предложение join](../../../language-reference/keywords/join-clause.md).)|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`join … in … on … equals …`<br /><br /> (Дополнительные сведения см. в разделе [Предложение join](../../../language-reference/keywords/join-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby`<br /><br /> (Дополнительные сведения см. в разделе [Предложение orderby](../../../language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby … descending`<br /><br /> (Дополнительные сведения см. в разделе [Предложение orderby](../../../language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.Select%2A>|`select`<br /><br /> (Дополнительные сведения см. в разделе [Предложение select](../../../language-reference/keywords/select-clause.md).)|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|Несколько предложений `from`.<br /><br /> (Дополнительные сведения см. в разделе [Предложение from](../../../language-reference/keywords/from-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, …`<br /><br /> (Дополнительные сведения см. в разделе [Предложение orderby](../../../language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, … descending`<br /><br /> (Дополнительные сведения см. в разделе [Предложение orderby](../../../language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.Where%2A>|`where`<br /><br /> (Дополнительные сведения см. в разделе [Предложение where](../../../language-reference/keywords/where-clause.md).)|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [Общие сведения о стандартных операторах запроса (C#)](./standard-query-operators-overview.md)
- [Классификация стандартных операторов запросов по способу выполнения (C#)](./classification-of-standard-query-operators-by-manner-of-execution.md)
