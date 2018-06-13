---
title: Практическое руководство. Представление вычисляемых столбцов
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: c53c781e8d4ec6836e032120816c3ef55de2ae0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353114"
---
# <a name="how-to-represent-computed-columns"></a>Практическое руководство. Представление вычисляемых столбцов
Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута, представляющего столбец, содержимое которого являются результатом вычисления.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает вычисляемые столбцы в качестве первичных ключей.  
  
### <a name="to-represent-a-computed-column"></a>Представление вычисляемого столбца  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Присвойте атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> строковое представление формулы.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Практическое руководство. Настройка классов сущностей с использованием редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
