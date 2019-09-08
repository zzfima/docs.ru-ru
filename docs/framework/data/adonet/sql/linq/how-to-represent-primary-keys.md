---
title: Практическое руководство. Как представить первичные ключи
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 5df82292f000d7f5e61cab699237b86de30bda70
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793429"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="b51e8-102">Практическое руководство. Как представить первичные ключи</span><span class="sxs-lookup"><span data-stu-id="b51e8-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="b51e8-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Используйте<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> свойство атрибута<xref:System.Data.Linq.Mapping.ColumnAttribute> , чтобы назначить свойство или поле для представления первичного ключа столбца базы данных.</span><span class="sxs-lookup"><span data-stu-id="b51e8-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="b51e8-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="b51e8-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b51e8-105">не поддерживает вычисляемые столбцы в качестве первичных ключей.</span><span class="sxs-lookup"><span data-stu-id="b51e8-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="b51e8-106">Назначение свойства или поля в качестве первичного ключа</span><span class="sxs-lookup"><span data-stu-id="b51e8-106">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="b51e8-107">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b51e8-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="b51e8-108">В качестве значения задайте `true`.</span><span class="sxs-lookup"><span data-stu-id="b51e8-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b51e8-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b51e8-109">See also</span></span>

- [<span data-ttu-id="b51e8-110">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b51e8-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="b51e8-111">Практическое руководство. Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="b51e8-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
