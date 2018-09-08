---
title: Как включить доступ к службе данных (службы WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: eb9d7cd8e62a73f49fd2b0f2fc2572b01109553b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44214840"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a>Как включить доступ к службе данных (службы WCF Data Services)
В службах [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] требуется явно предоставлять доступ к ресурсам, предоставляемым службой данных. Это значит, что после создания новой службы данных все равно требуется явно предоставлять доступ к отдельным ресурсам в виде набора сущностей. В этом разделе показано, как включить чтения и задает доступ на запись к пяти сущности в службе данных Northwind, которая создается при завершении [быстрого запуска](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Поскольку перечисление <xref:System.Data.Services.EntitySetRights> определяется с помощью <xref:System.FlagsAttribute>, для указания нескольких разрешений для одного набора сущностей или операции можно использовать логический оператор OR.  
  
> [!NOTE]
>  Любой клиент, имеющий доступ к приложению ASP.NET, имеет также доступ к ресурсам, предоставляемым службой данных. Для предотвращения несанкционированного доступа к ресурсам производственной службы данных необходимо также установить защиту самого приложения. Дополнительные сведения см. в разделе [NIB: безопасность ASP.NET](https://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d).  
  
### <a name="to-enable-access-to-the-data-service"></a>Включение доступа к службе данных  
  
-   В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     Это обеспечивает клиентам доступ для чтения и записи к наборам сущностей `Orders` и `Order_Details` и доступ только для чтения к наборам сущностей `Customers`.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Разработка службы данных WCF Data Service, работающей на IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)  
 [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
