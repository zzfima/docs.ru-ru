---
title: Практическое руководство. Как представить столбцы как столбцы отметки времени или версии
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: ef99e0420b328f94686e08256ecf229000467810
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793498"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a>Практическое руководство. Как представить столбцы как столбцы отметки времени или версии
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Используйте<xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> свойство атрибута<xref:System.Data.Linq.Mapping.ColumnAttribute> для обозначения поля или свойства, представляющего столбец базы данных, который содержит метки времени базы данных или номера версий.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a>Назначение поля или свойства, представляющего столбец версии или отметки времени  
  
1. Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> значение `true`.  
  
## <a name="see-also"></a>См. также

- [Модель объектов LINQ to SQL](the-linq-to-sql-object-model.md)
- [Практическое руководство. Укажите, какие элементы проверяются на конфликты параллелизма](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [Практическое руководство. Настройка классов сущностей с помощью редактора кода](how-to-customize-entity-classes-by-using-the-code-editor.md)
