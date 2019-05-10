---
title: Практическое руководство. Как представить таблицы в виде классов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: ff943fbc7ae137128d6c635fd2366ad14cf70d15
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620021"
---
# <a name="how-to-represent-tables-as-classes"></a>Практическое руководство. Как представить таблицы в виде классов
Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> атрибут, чтобы задать класс как класс сущности, связанный с таблицей базы данных.  
  
### <a name="to-map-a-class-to-a-database-table"></a>Сопоставление класса с таблицей базы данных  
  
- Добавьте в объявление класса атрибут <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
## <a name="example"></a>Пример  
 Следующий код определяет класс `Customer` как класс сущности, связанный с таблицей базы данных `Customers`.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 Если можно определить имя, указывать свойство <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> нет необходимости. Если имя не указано, оно будет считаться совпадающим с именем свойства или поля.  
  
## <a name="see-also"></a>См. также

- [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Практическое руководство. Настройка классов сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
