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
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="74722-102">Практическое руководство. Как представить таблицы в виде классов</span><span class="sxs-lookup"><span data-stu-id="74722-102">How to: Represent Tables as Classes</span></span>
<span data-ttu-id="74722-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> атрибут, чтобы задать класс как класс сущности, связанный с таблицей базы данных.</span><span class="sxs-lookup"><span data-stu-id="74722-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="74722-104">Сопоставление класса с таблицей базы данных</span><span class="sxs-lookup"><span data-stu-id="74722-104">To map a class to a database table</span></span>  
  
- <span data-ttu-id="74722-105">Добавьте в объявление класса атрибут <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="74722-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74722-106">Пример</span><span class="sxs-lookup"><span data-stu-id="74722-106">Example</span></span>  
 <span data-ttu-id="74722-107">Следующий код определяет класс `Customer` как класс сущности, связанный с таблицей базы данных `Customers`.</span><span class="sxs-lookup"><span data-stu-id="74722-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="74722-108">Если можно определить имя, указывать свойство <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="74722-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="74722-109">Если имя не указано, оно будет считаться совпадающим с именем свойства или поля.</span><span class="sxs-lookup"><span data-stu-id="74722-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74722-110">См. также</span><span class="sxs-lookup"><span data-stu-id="74722-110">See also</span></span>

- [<span data-ttu-id="74722-111">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="74722-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="74722-112">Практическое руководство. Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="74722-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
