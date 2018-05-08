---
title: Практическое руководство. Представление первичных ключей
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: dae8603a18318f45182c7148b10b8194e67fd017
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-represent-primary-keys"></a>Практическое руководство. Представление первичных ключей
Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибут, чтобы назначить свойство или поле для представления первичного ключа для столбца базы данных.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает вычисляемые столбцы в качестве первичных ключей.  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a>Назначение свойства или поля в качестве первичного ключа  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  В качестве значения задайте `true`.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Практическое руководство. Настройка классов сущностей с использованием редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
