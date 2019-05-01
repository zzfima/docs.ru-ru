---
title: Практическое руководство. Как организовать проверку наличия конфликтов параллелизма
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
ms.openlocfilehash: 53d3ba6969705940c403795d3764c021f0829c64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033687"
---
# <a name="how-to-specify-concurrency-conflict-checking"></a>Практическое руководство. Как организовать проверку наличия конфликтов параллелизма
Можно указать, какие столбцы базы данных должны проверяться на наличие конфликтов параллелизма при вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Дополнительные сведения см. в разделе [Как Укажите, какие элементы проверяются на наличие конфликтов параллелизма](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода указывается, что член `HomePage` никогда не должен включаться в проверки обновлений. Дополнительные сведения см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Практическое руководство. Настройка классов сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
