---
title: "Практическое руководство. Представление первичных ключей"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3510d52f6f6de9ee2e99ebc1e9fc6fa581d58f3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="2f208-102">Практическое руководство. Представление первичных ключей</span><span class="sxs-lookup"><span data-stu-id="2f208-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="2f208-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибут, чтобы назначить свойство или поле для представления первичного ключа для столбца базы данных.</span><span class="sxs-lookup"><span data-stu-id="2f208-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="2f208-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="2f208-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="2f208-105"> не поддерживает вычисляемые столбцы в качестве первичных ключей.</span><span class="sxs-lookup"><span data-stu-id="2f208-105"> does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="2f208-106">Назначение свойства или поля в качестве первичного ключа</span><span class="sxs-lookup"><span data-stu-id="2f208-106">To designate a property or field as a primary key</span></span>  
  
1.  <span data-ttu-id="2f208-107">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2f208-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="2f208-108">В качестве значения задайте `true`.</span><span class="sxs-lookup"><span data-stu-id="2f208-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f208-109">См. также</span><span class="sxs-lookup"><span data-stu-id="2f208-109">See Also</span></span>  
 [<span data-ttu-id="2f208-110">LINQ to SQL модель объектов</span><span class="sxs-lookup"><span data-stu-id="2f208-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="2f208-111">Как: Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="2f208-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
