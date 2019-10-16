---
title: Публикация конечных точек метаданных
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 4c6ac81f0c97415dc21ff3346178dd1e9936b7a5
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319899"
---
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="1671f-102">Публикация конечных точек метаданных</span><span class="sxs-lookup"><span data-stu-id="1671f-102">Publishing Metadata Endpoints</span></span>
<span data-ttu-id="1671f-103">Службы Windows Communication Foundation (WCF) публикуют метаданные путем публикации одной или нескольких конечных точек метаданных.</span><span class="sxs-lookup"><span data-stu-id="1671f-103">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="1671f-104">Публикация метаданных службы позволяет получать доступ к метаданным с использованием стандартных протоколов, таких как WS-MetadataExchange (MEX) и запросы HTTP/GET.</span><span class="sxs-lookup"><span data-stu-id="1671f-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="1671f-105">Конечные точки подобны другим конечным точкам служб в том, что они имеют адрес, привязку и контракт, и могут быть добавлены в ведущее приложение службы посредством конфигурации или в коде.</span><span class="sxs-lookup"><span data-stu-id="1671f-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="1671f-106">Для публикации конечных точек метаданных необходимо добавить в службу поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="1671f-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1671f-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="1671f-107">In This Section</span></span>  
 [<span data-ttu-id="1671f-108">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="1671f-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="1671f-109">Демонстрирует настройку службы WCF для публикации метаданных, чтобы клиенты могли получать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET, используя строку запроса `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="1671f-109">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="1671f-110">Практическое руководство. Публикация метаданных для службы с использованием кода</span><span class="sxs-lookup"><span data-stu-id="1671f-110">How to: Publish Metadata for a Service Using Code</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="1671f-111">Демонстрирует, как включить публикацию метаданных для службы WCF в коде, чтобы клиенты могли получать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET, используя строку запроса `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="1671f-111">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1671f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1671f-112">See also</span></span>

- [<span data-ttu-id="1671f-113">Публикация метаданных</span><span class="sxs-lookup"><span data-stu-id="1671f-113">Publishing Metadata</span></span>](./feature-details/publishing-metadata.md)
