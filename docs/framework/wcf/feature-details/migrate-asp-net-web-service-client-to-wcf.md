---
title: "Практическое руководство. Миграция кода клиента веб-службы ASP.NET на платформу Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b93460fd6d331b43b49f10cf78fc8863ca1d8d88
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a><span data-ttu-id="69524-102">Практическое руководство. Миграция кода клиента веб-службы ASP.NET на платформу Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="69524-102">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="69524-103">В следующей процедуре в общих чертах описывается порядок переноса кода клиента веб-службы ASP.NET на платформу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69524-103">The following procedure describes the broad steps that need to be followed to migrate ASP.NET Web Service client code to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="69524-104">Процедура</span><span class="sxs-lookup"><span data-stu-id="69524-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a><span data-ttu-id="69524-105">Миграция кода клиента службы ASP.NET в WCF</span><span class="sxs-lookup"><span data-stu-id="69524-105">To migrate ASP.NET Web Service client code to WCF</span></span>  
  
1.  <span data-ttu-id="69524-106">Убедитесь в наличии комплексного набора тестов для клиента.</span><span class="sxs-lookup"><span data-stu-id="69524-106">Ensure that a comprehensive set of tests exist for the client.</span></span>  
  
2.  <span data-ttu-id="69524-107">С помощью Visual Studio 2005 обновите клиентское приложение до .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="69524-107">Use Visual Studio 2005 to upgrade the client application to .NET 2.0.</span></span> <span data-ttu-id="69524-108">Выполните набор тестов.</span><span class="sxs-lookup"><span data-stu-id="69524-108">Run the set of tests.</span></span>  
  
3.  <span data-ttu-id="69524-109">Удалите код клиента ASP.NET из клиентского проекта.</span><span class="sxs-lookup"><span data-stu-id="69524-109">Remove ASP.NET client code from the client project.</span></span> <span data-ttu-id="69524-110">Этот код находится в модулях, сформированных с помощью программы WSDL.exe.</span><span class="sxs-lookup"><span data-stu-id="69524-110">That code is in modules generated using the WSDL.exe tool.</span></span>  
  
4.  <span data-ttu-id="69524-111">Создание [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] кода клиента с помощью [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="69524-111">Generate [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client code using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="69524-112">Добавьте этот код в клиентский проект и объедините полученную конфигурацию с существующим файлом конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="69524-112">Add that code to the client project and merge the configuration output into the client’s existing configuration file.</span></span>  
  
5.  <span data-ttu-id="69524-113">Скомпилируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="69524-113">Compile the application.</span></span> <span data-ttu-id="69524-114">Исправьте ошибки компиляции, заменив ссылки на старые клиентские типы ASP.NET ссылками на новые клиентские типы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69524-114">Repair the compilation errors by replacing references to the former ASP.NET client types with references to the new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client types.</span></span>  
  
6.  <span data-ttu-id="69524-115">Выполните набор тестов.</span><span class="sxs-lookup"><span data-stu-id="69524-115">Run the set of tests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69524-116">См. также</span><span class="sxs-lookup"><span data-stu-id="69524-116">See Also</span></span>  
 [<span data-ttu-id="69524-117">Как: перенос кода службы ASP.NET на платформу Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="69524-117">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
