---
title: Практическое руководство. Разрешение доступа к службе данных (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: 82b2ec9313c6e0d4b9fa05862209a3ea838f31fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918624"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a>Практическое руководство. Разрешение доступа к службе данных (WCF Data Services)
В службах [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] требуется явно предоставлять доступ к ресурсам, предоставляемым службой данных. Это значит, что после создания новой службы данных все равно требуется явно предоставлять доступ к отдельным ресурсам в виде набора сущностей. В этом разделе показано, как включить доступ на чтение и запись к пяти наборам сущностей в службе данных Northwind, которая создается при завершении [краткого руководства](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Поскольку перечисление <xref:System.Data.Services.EntitySetRights> определяется с помощью <xref:System.FlagsAttribute>, для указания нескольких разрешений для одного набора сущностей или операции можно использовать логический оператор OR.  
  
> [!NOTE]
> Любой клиент, имеющий доступ к приложению ASP.NET, имеет также доступ к ресурсам, предоставляемым службой данных. Для предотвращения несанкционированного доступа к ресурсам производственной службы данных необходимо также установить защиту самого приложения. Дополнительные сведения см. в статье [Защита веб-сайтов ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/91f66yxt(v=vs.100)).  
  
### <a name="to-enable-access-to-the-data-service"></a>Включение доступа к службе данных  
  
- В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]  
  
     Это обеспечивает клиентам доступ для чтения и записи к наборам сущностей `Orders` и `Order_Details` и доступ только для чтения к наборам сущностей `Customers`.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Разработка службы данных WCF, работающей на IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)
- [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
