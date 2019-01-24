---
title: Как выполнить указать типы данных базы данных
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: 566ff545cd493eed637093c378aacc865a7f5e20
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620491"
---
# <a name="how-to-specify-database-data-types"></a><span data-ttu-id="71a3e-102">Как выполнить указать типы данных базы данных</span><span class="sxs-lookup"><span data-stu-id="71a3e-102">How to: Specify Database Data Types</span></span>
<span data-ttu-id="71a3e-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибут для задания точного текста, определяющего столбец в объявлении таблицы T-SQL.</span><span class="sxs-lookup"><span data-stu-id="71a3e-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify the exact text that defines the column in a T-SQL table declaration.</span></span>  
  
 <span data-ttu-id="71a3e-104">Свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> следует задавать, только если для создания экземпляра базы данных планируется использовать <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span><span class="sxs-lookup"><span data-stu-id="71a3e-104">You must specify the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property only if you plan to use <xref:System.Data.Linq.DataContext.CreateDatabase%2A> to create an instance of the database.</span></span>  
  
 <span data-ttu-id="71a3e-105">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="71a3e-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a><span data-ttu-id="71a3e-106">Задание текста для определения типа данных в таблице T-SQL</span><span class="sxs-lookup"><span data-stu-id="71a3e-106">To specify text to define a data type in a T-SQL table</span></span>  
  
1.  <span data-ttu-id="71a3e-107">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="71a3e-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="71a3e-108">В качестве значения свойства <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> укажите точный текст, используемый T-SQL.</span><span class="sxs-lookup"><span data-stu-id="71a3e-108">Set the value of the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the exact text that is used by T-SQL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a3e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="71a3e-109">See also</span></span>
- [<span data-ttu-id="71a3e-110">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="71a3e-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="71a3e-111">Практическое руководство. Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="71a3e-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
