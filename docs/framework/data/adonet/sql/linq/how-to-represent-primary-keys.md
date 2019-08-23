---
title: Практическое руководство. Как представить первичные ключи
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 28c62798f965edfcffe1a156213c2481a8193b49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943531"
---
# <a name="how-to-represent-primary-keys"></a>Практическое руководство. Как представить первичные ключи
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Используйте<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> свойство атрибута<xref:System.Data.Linq.Mapping.ColumnAttribute> , чтобы назначить свойство или поле для представления первичного ключа столбца базы данных.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает вычисляемые столбцы в качестве первичных ключей.  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a>Назначение свойства или поля в качестве первичного ключа  
  
1. Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. В качестве значения задайте `true`.  
  
## <a name="see-also"></a>См. также

- [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Практическое руководство. Настройка классов сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
