---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 15ae13563cfcfb3765559cafb2d31bd6482df7b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767316"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="40c6e-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="40c6e-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="40c6e-103">Требуется сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="40c6e-103">Client certificate is required.</span></span> <span data-ttu-id="40c6e-104">В запросе не было найдено ни одного сертификата.</span><span class="sxs-lookup"><span data-stu-id="40c6e-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="40c6e-105">Описание</span><span class="sxs-lookup"><span data-stu-id="40c6e-105">Description</span></span>  
 <span data-ttu-id="40c6e-106">Эта трассировка показывает, что прослушиватель HTTPS получил запрос HTTPS, который не был связан с сертификатом клиента.</span><span class="sxs-lookup"><span data-stu-id="40c6e-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="40c6e-107">Так как прослушиватель был настроен на требование сертификатов клиента от всех запросов HTTPS, прослушивателю не удалось проверить подлинность клиента.</span><span class="sxs-lookup"><span data-stu-id="40c6e-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c6e-108">См. также</span><span class="sxs-lookup"><span data-stu-id="40c6e-108">See also</span></span>

- [<span data-ttu-id="40c6e-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="40c6e-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="40c6e-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="40c6e-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="40c6e-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="40c6e-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
