---
title: Как включить доступ к службе данных (службы WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: 0ec9c9a730516b22b4eaa215e042e9393c01d752
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569109"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a><span data-ttu-id="6886a-102">Как включить доступ к службе данных (службы WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="6886a-102">How to: Enable Access to the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="6886a-103">В WCF Data Services необходимо явно предоставить доступ к ресурсам, предоставляемым службой данных.</span><span class="sxs-lookup"><span data-stu-id="6886a-103">In WCF Data Services, you must explicitly grant access to the resources that are exposed by a data service.</span></span> <span data-ttu-id="6886a-104">Это значит, что после создания новой службы данных все равно требуется явно предоставлять доступ к отдельным ресурсам в виде набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="6886a-104">This means that after you create a new data service, you must still explicitly provide access to individual resources as entity sets.</span></span> <span data-ttu-id="6886a-105">В этом разделе показано, как включить доступ на чтение и запись к пяти наборам сущностей в службе данных Northwind, которая создается при завершении [краткого руководства](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6886a-105">This topic shows how to enable read and write access to five of the entity sets in the Northwind data service that is created when you complete the [quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="6886a-106">Поскольку перечисление <xref:System.Data.Services.EntitySetRights> определяется с помощью <xref:System.FlagsAttribute>, для указания нескольких разрешений для одного набора сущностей или операции можно использовать логический оператор OR.</span><span class="sxs-lookup"><span data-stu-id="6886a-106">Because the <xref:System.Data.Services.EntitySetRights> enumeration is defined by using the <xref:System.FlagsAttribute>, you can use a logical OR operator to specify multiple permissions for a single entity set.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6886a-107">Любой клиент, имеющий доступ к приложению ASP.NET, имеет также доступ к ресурсам, предоставляемым службой данных.</span><span class="sxs-lookup"><span data-stu-id="6886a-107">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="6886a-108">Для предотвращения несанкционированного доступа к ресурсам производственной службы данных необходимо также установить защиту самого приложения.</span><span class="sxs-lookup"><span data-stu-id="6886a-108">In a production data service, to prevent unauthorized access to resources, you should also secure the application itself.</span></span> <span data-ttu-id="6886a-109">Дополнительные сведения см. в статье [Защита веб-сайтов ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/91f66yxt(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6886a-109">For more information, see [Securing ASP.NET Web Sites](https://docs.microsoft.com/previous-versions/aspnet/91f66yxt(v=vs.100)).</span></span>  
  
### <a name="to-enable-access-to-the-data-service"></a><span data-ttu-id="6886a-110">Включение доступа к службе данных</span><span class="sxs-lookup"><span data-stu-id="6886a-110">To enable access to the data service</span></span>  
  
- <span data-ttu-id="6886a-111">В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:</span><span class="sxs-lookup"><span data-stu-id="6886a-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="6886a-112">Это обеспечивает клиентам доступ для чтения и записи к наборам сущностей `Orders` и `Order_Details` и доступ только для чтения к наборам сущностей `Customers`.</span><span class="sxs-lookup"><span data-stu-id="6886a-112">This enables clients to have read and write access to the `Orders` and `Order_Details` entity sets and read-only access to the `Customers` entity sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6886a-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="6886a-113">See also</span></span>

- [<span data-ttu-id="6886a-114">Практическое руководство. Разработка службы данных WCF Data Service, работающей на IIS</span><span class="sxs-lookup"><span data-stu-id="6886a-114">How to: Develop a WCF Data Service Running on IIS</span></span>](how-to-develop-a-wcf-data-service-running-on-iis.md)
- [<span data-ttu-id="6886a-115">Настройка службы данных</span><span class="sxs-lookup"><span data-stu-id="6886a-115">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)
