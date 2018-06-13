---
title: Практическое руководство. Миграция кода клиента веб-службы ASP.NET на платформу Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
ms.openlocfilehash: cb60f9cb2e8f35ee703b049eae9e3d99c1ec7d49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491134"
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a><span data-ttu-id="ea847-102">Практическое руководство. Миграция кода клиента веб-службы ASP.NET на платформу Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ea847-102">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="ea847-103">Следующая процедура описывает общих действия, которые необходимо соблюдать порядок переноса кода клиента веб-службы ASP.NET в WCF.</span><span class="sxs-lookup"><span data-stu-id="ea847-103">The following procedure describes the broad steps that need to be followed to migrate ASP.NET Web Service client code to WCF.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="ea847-104">Процедура</span><span class="sxs-lookup"><span data-stu-id="ea847-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a><span data-ttu-id="ea847-105">Миграция кода клиента службы ASP.NET в WCF</span><span class="sxs-lookup"><span data-stu-id="ea847-105">To migrate ASP.NET Web Service client code to WCF</span></span>  
  
1.  <span data-ttu-id="ea847-106">Убедитесь в наличии комплексного набора тестов для клиента.</span><span class="sxs-lookup"><span data-stu-id="ea847-106">Ensure that a comprehensive set of tests exist for the client.</span></span>  
  
2.  <span data-ttu-id="ea847-107">С помощью Visual Studio 2005 обновите клиентское приложение до .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="ea847-107">Use Visual Studio 2005 to upgrade the client application to .NET 2.0.</span></span> <span data-ttu-id="ea847-108">Выполните набор тестов.</span><span class="sxs-lookup"><span data-stu-id="ea847-108">Run the set of tests.</span></span>  
  
3.  <span data-ttu-id="ea847-109">Удалите код клиента ASP.NET из клиентского проекта.</span><span class="sxs-lookup"><span data-stu-id="ea847-109">Remove ASP.NET client code from the client project.</span></span> <span data-ttu-id="ea847-110">Этот код находится в модулях, сформированных с помощью программы WSDL.exe.</span><span class="sxs-lookup"><span data-stu-id="ea847-110">That code is in modules generated using the WSDL.exe tool.</span></span>  
  
4.  <span data-ttu-id="ea847-111">Создание кода клиента WCF с помощью [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ea847-111">Generate WCF client code using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="ea847-112">Добавьте этот код в клиентский проект и объедините полученную конфигурацию с существующим файлом конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="ea847-112">Add that code to the client project and merge the configuration output into the client’s existing configuration file.</span></span>  
  
5.  <span data-ttu-id="ea847-113">Скомпилируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="ea847-113">Compile the application.</span></span> <span data-ttu-id="ea847-114">Исправьте ошибки компиляции, заменив ссылки на старые клиентские типы ASP.NET со ссылками на новые типы клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="ea847-114">Repair the compilation errors by replacing references to the former ASP.NET client types with references to the new WCF client types.</span></span>  
  
6.  <span data-ttu-id="ea847-115">Выполните набор тестов.</span><span class="sxs-lookup"><span data-stu-id="ea847-115">Run the set of tests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea847-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ea847-116">See Also</span></span>  
 [<span data-ttu-id="ea847-117">Практическое руководство. Миграция кода веб-службы ASP.NET на платформу Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ea847-117">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
