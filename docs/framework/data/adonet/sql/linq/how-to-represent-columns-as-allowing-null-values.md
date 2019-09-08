---
title: Практическое руководство. Как представлять столбцы, допускающие значения NULL
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: 00a837467010c2d8a9f0ca16d6aba2fc5f4c973f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781805"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a>Практическое руководство. Как представлять столбцы, допускающие значения NULL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Используйте<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> свойство атрибута<xref:System.Data.Linq.Mapping.ColumnAttribute> , чтобы указать, что в связанном столбце базы данных могут храниться значения NULL.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a>Включение для столбца возможности содержать значения NULL  
  
1. Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> значение `true`.  
  
## <a name="see-also"></a>См. также

- [Модель объектов LINQ to SQL](the-linq-to-sql-object-model.md)
- [Практическое руководство. Настройка классов сущностей с помощью редактора кода](how-to-customize-entity-classes-by-using-the-code-editor.md)
