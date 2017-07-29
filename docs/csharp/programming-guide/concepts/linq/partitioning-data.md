---
title: "Секционирование данных (C#)"
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
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
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
ms.openlocfilehash: 2f1690dac93d5e74f1305bd457f8bc749bec5449
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="partitioning-data-c"></a>Секционирование данных (C#)
Секционированием в LINQ называют операцию разделения входной последовательности на два раздела без изменения порядка элементов, а затем возвращения одного из разделов.  
  
 На следующем рисунке показаны результаты трех различных операций секционирования в последовательности символов. Первая операция возвращает первые три элемента в последовательности. Вторая операция пропускает первые три элемента и возвращает остальные элементы. Третья операция пропускает первые два элемента в последовательности и возвращает три следующих элемента.  
  
 ![Операции секционирования LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")  
  
 Далее перечислены методы стандартных операторов запроса, которые секционируют последовательности.  
  
## <a name="operators"></a>Операторы  
  
|Имя оператора|Описание|Синтаксис выражения запроса C#|Дополнительные сведения|  
|-------------------|-----------------|---------------------------------|----------------------|  
|Пропустить|Пропускает элементы до указанной позиции в последовательности.|Неприменимо.|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName>|  
|SkipWhile|Пропускает элементы, пока элемент не удовлетворит условию функции предиката.|Неприменимо.|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName>|  
|Take|Возвращает элементы на указанную позицию в последовательности.|Неприменимо.|<xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=fullName>|  
|TakeWhile|Принимает элементы, пока элемент не удовлетворит условию функции предиката.|Неприменимо.|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq>   
 [Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)

