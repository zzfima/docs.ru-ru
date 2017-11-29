---
title: "Практическое руководство. Указание имен баз данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 998a720f4e2cd7c3a63578d1025d0dd7b42a1b92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-database-names"></a><span data-ttu-id="b8883-102">Практическое руководство. Указание имен баз данных</span><span class="sxs-lookup"><span data-stu-id="b8883-102">How to: Specify Database Names</span></span>
<span data-ttu-id="b8883-103">Для указания имени базы данных, если это имя не предоставлено во время подключения, используется свойство <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> атрибута <xref:System.Data.Linq.Mapping.DatabaseAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b8883-103">Use the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property on a <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to specify the name of a database when a name is not supplied by the connection.</span></span>  
  
 <span data-ttu-id="b8883-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="b8883-104">For code samples, see <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-the-database"></a><span data-ttu-id="b8883-105">Указание имени базы данных</span><span class="sxs-lookup"><span data-stu-id="b8883-105">To specify the name of the database</span></span>  
  
1.  <span data-ttu-id="b8883-106">Добавьте атрибут <xref:System.Data.Linq.Mapping.DatabaseAttribute> к объявлению класса для базы данных.</span><span class="sxs-lookup"><span data-stu-id="b8883-106">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to the class declaration for the database.</span></span>  
  
2.  <span data-ttu-id="b8883-107">Добавьте свойство <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> атрибуту <xref:System.Data.Linq.Mapping.DatabaseAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b8883-107">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property to the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="b8883-108">Установите для свойства <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> значение имени, которое необходимо указать.</span><span class="sxs-lookup"><span data-stu-id="b8883-108">Set the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property value to the name that you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8883-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b8883-109">See Also</span></span>  
 [<span data-ttu-id="b8883-110">LINQ to SQL модель объектов</span><span class="sxs-lookup"><span data-stu-id="b8883-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="b8883-111">Как: Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="b8883-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
