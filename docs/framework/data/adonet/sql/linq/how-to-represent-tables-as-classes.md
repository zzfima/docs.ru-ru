---
title: Как выполнить представить таблицы в виде классов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 307356e056aae29af7c8ceafae0ca02604658aab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509614"
---
# <a name="how-to-represent-tables-as-classes"></a>Как выполнить представить таблицы в виде классов
Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> атрибут, чтобы задать класс как класс сущности, связанный с таблицей базы данных.  
  
### <a name="to-map-a-class-to-a-database-table"></a>Сопоставление класса с таблицей базы данных  
  
-   Добавьте в объявление класса атрибут <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
## <a name="example"></a>Пример  
 Следующий код определяет класс `Customer` как класс сущности, связанный с таблицей базы данных `Customers`.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 Если можно определить имя, указывать свойство <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> нет необходимости. Если имя не указано, оно будет считаться совпадающим с именем свойства или поля.  
  
## <a name="see-also"></a>См. также
- [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Практическое руководство. Настройка классов сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
