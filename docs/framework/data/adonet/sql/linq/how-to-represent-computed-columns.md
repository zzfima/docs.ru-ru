---
title: Практическое руководство. Как представить вычисляемые столбцы
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: 7b37e698419fae7590ac1853309a7f394917f6a0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781735"
---
# <a name="how-to-represent-computed-columns"></a>Практическое руководство. Как представить вычисляемые столбцы
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Используйте<xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> свойство атрибута<xref:System.Data.Linq.Mapping.ColumnAttribute> для представления столбца, содержимое которого является результатом вычисления.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает вычисляемые столбцы в качестве первичных ключей.  
  
### <a name="to-represent-a-computed-column"></a>Представление вычисляемого столбца  
  
1. Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Присвойте атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> строковое представление формулы.  
  
## <a name="see-also"></a>См. также

- [Модель объектов LINQ to SQL](the-linq-to-sql-object-model.md)
- [Практическое руководство. Настройка классов сущностей с помощью редактора кода](how-to-customize-entity-classes-by-using-the-code-editor.md)
