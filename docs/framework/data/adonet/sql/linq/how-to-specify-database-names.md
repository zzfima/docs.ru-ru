---
title: Практическое руководство. Как указывать имена баз данных
ms.date: 03/30/2017
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
ms.openlocfilehash: 1c694678dc3a60cf91dea62f2a17973b396e2b19
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184526"
---
# <a name="how-to-specify-database-names"></a><span data-ttu-id="c32c6-102">Практическое руководство. Как указывать имена баз данных</span><span class="sxs-lookup"><span data-stu-id="c32c6-102">How to: Specify Database Names</span></span>
<span data-ttu-id="c32c6-103">Для указания имени базы данных, если это имя не предоставлено во время подключения, используется свойство <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> атрибута <xref:System.Data.Linq.Mapping.DatabaseAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c32c6-103">Use the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property on a <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to specify the name of a database when a name is not supplied by the connection.</span></span>  
  
 <span data-ttu-id="c32c6-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="c32c6-104">For code samples, see <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-the-database"></a><span data-ttu-id="c32c6-105">Указание имени базы данных</span><span class="sxs-lookup"><span data-stu-id="c32c6-105">To specify the name of the database</span></span>  
  
1.  <span data-ttu-id="c32c6-106">Добавьте атрибут <xref:System.Data.Linq.Mapping.DatabaseAttribute> к объявлению класса для базы данных.</span><span class="sxs-lookup"><span data-stu-id="c32c6-106">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to the class declaration for the database.</span></span>  
  
2.  <span data-ttu-id="c32c6-107">Добавьте свойство <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> атрибуту <xref:System.Data.Linq.Mapping.DatabaseAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c32c6-107">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property to the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="c32c6-108">Установите для свойства <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> значение имени, которое необходимо указать.</span><span class="sxs-lookup"><span data-stu-id="c32c6-108">Set the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property value to the name that you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c32c6-109">См. также</span><span class="sxs-lookup"><span data-stu-id="c32c6-109">See also</span></span>

- [<span data-ttu-id="c32c6-110">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c32c6-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="c32c6-111">Практическое руководство. Как настроить классы сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="c32c6-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
