---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 15ae13563cfcfb3765559cafb2d31bd6482df7b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201186"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="e560f-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="e560f-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="e560f-103">Требуется сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="e560f-103">Client certificate is required.</span></span> <span data-ttu-id="e560f-104">В запросе не было найдено ни одного сертификата.</span><span class="sxs-lookup"><span data-stu-id="e560f-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e560f-105">Описание</span><span class="sxs-lookup"><span data-stu-id="e560f-105">Description</span></span>  
 <span data-ttu-id="e560f-106">Эта трассировка показывает, что прослушиватель HTTPS получил запрос HTTPS, который не был связан с сертификатом клиента.</span><span class="sxs-lookup"><span data-stu-id="e560f-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="e560f-107">Так как прослушиватель был настроен на требование сертификатов клиента от всех запросов HTTPS, прослушивателю не удалось проверить подлинность клиента.</span><span class="sxs-lookup"><span data-stu-id="e560f-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e560f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e560f-108">See also</span></span>

- [<span data-ttu-id="e560f-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="e560f-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="e560f-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="e560f-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e560f-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="e560f-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
