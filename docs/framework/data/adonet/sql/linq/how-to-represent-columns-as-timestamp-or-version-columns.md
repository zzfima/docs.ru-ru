---
title: Как выполнить представить столбцы как столбцы отметки времени или версии
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: fa9ffe01c45df3ce0342b62e12007ddf88ee412d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674574"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="15d5b-102">Как выполнить представить столбцы как столбцы отметки времени или версии</span><span class="sxs-lookup"><span data-stu-id="15d5b-102">How to: Represent Columns as Timestamp or Version Columns</span></span>
<span data-ttu-id="15d5b-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибут назначение поля или свойства, представляющего столбец базы данных, содержащий базы данных отметки времени или номера версий.</span><span class="sxs-lookup"><span data-stu-id="15d5b-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="15d5b-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="15d5b-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="15d5b-105">Назначение поля или свойства, представляющего столбец версии или отметки времени</span><span class="sxs-lookup"><span data-stu-id="15d5b-105">To designate a field or property as representing a timestamp or version column</span></span>  
  
1.  <span data-ttu-id="15d5b-106">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="15d5b-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="15d5b-107">Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="15d5b-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15d5b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="15d5b-108">See also</span></span>
- [<span data-ttu-id="15d5b-109">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="15d5b-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="15d5b-110">Практическое руководство. Укажите, каких элементов тестируется возникновение конфликтов параллелизма</span><span class="sxs-lookup"><span data-stu-id="15d5b-110">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [<span data-ttu-id="15d5b-111">Практическое руководство. Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="15d5b-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
