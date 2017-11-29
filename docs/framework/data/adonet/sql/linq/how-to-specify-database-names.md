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
# <a name="how-to-specify-database-names"></a>Практическое руководство. Указание имен баз данных
Для указания имени базы данных, если это имя не предоставлено во время подключения, используется свойство <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> атрибута <xref:System.Data.Linq.Mapping.DatabaseAttribute>.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.  
  
### <a name="to-specify-the-name-of-the-database"></a>Указание имени базы данных  
  
1.  Добавьте атрибут <xref:System.Data.Linq.Mapping.DatabaseAttribute> к объявлению класса для базы данных.  
  
2.  Добавьте свойство <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> атрибуту <xref:System.Data.Linq.Mapping.DatabaseAttribute>.  
  
3.  Установите для свойства <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> значение имени, которое необходимо указать.  
  
## <a name="see-also"></a>См. также  
 [LINQ to SQL модель объектов](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Как: Настройка классов сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
