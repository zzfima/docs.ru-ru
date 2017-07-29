---
title: "Операции с элементами (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 283206c9-3246-4c48-b01a-d9de409a7231
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: da747e884960c89fabc45d3761da92f913d66362
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="element-operations-c"></a>Операции с элементами (C#)
Операции с элементами возвращают один определенный элемент из последовательности.  
  
 В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции с элементами.  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание|Синтаксис выражения запроса C#|Дополнительные сведения|  
|-----------------|-----------------|---------------------------------|----------------------|  
|ElementAt|Возвращает элемент коллекции с указанным индексом.|Неприменимо.|<xref:System.Linq.Enumerable.ElementAt%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAt%2A?displayProperty=fullName>|  
|ElementAtOrDefault|Возвращает элемент коллекции с указанным индексом или значение по умолчанию, если индекс выходит за пределы допустимого диапазона.|Неприменимо.|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAtOrDefault%2A?displayProperty=fullName>|  
|First|Возвращает первый элемент коллекции или первый элемент, удовлетворяющий условию.|Неприменимо.|<xref:System.Linq.Enumerable.First%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.First%2A?displayProperty=fullName>|  
|FirstOrDefault|Возвращает первый элемент коллекции или первый элемент, удовлетворяющий условию. Если такой элемент не существует, возвращает значение по умолчанию.|Неприменимо.|<xref:System.Linq.Enumerable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%60%601%28System.Linq.IQueryable%7B%60%600%7D%29?displayProperty=fullName>|  
|Последняя|Возвращает последний элемент коллекции или последний элемент, удовлетворяющий условию.|Неприменимо.|<xref:System.Linq.Enumerable.Last%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Last%2A?displayProperty=fullName>|  
|LastOrDefault|Возвращает последний элемент коллекции или последний элемент, удовлетворяющий условию. Если такой элемент не существует, возвращает значение по умолчанию.|Неприменимо.|<xref:System.Linq.Enumerable.LastOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LastOrDefault%2A?displayProperty=fullName>|  
|Single|Возвращает единственный элемент коллекции или единственный элемент, удовлетворяющий условию.|Неприменимо.|<xref:System.Linq.Enumerable.Single%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Single%2A?displayProperty=fullName>|  
|SingleOrDefault|Возвращает единственный элемент коллекции или единственный элемент, удовлетворяющий условию. Если такой элемент отсутствует или коллекция содержит не один такой элемент, возвращает значение по умолчанию.|Неприменимо.|<xref:System.Linq.Enumerable.SingleOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SingleOrDefault%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq>   
 [Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Практическое руководство. Запрос самого большого файла или файлов в дереве папок (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)

