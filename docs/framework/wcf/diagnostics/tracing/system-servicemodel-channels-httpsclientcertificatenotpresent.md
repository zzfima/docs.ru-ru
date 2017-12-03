---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3a9eb867826fbf1e4028f57e5118ff18d4329b23
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="41590-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="41590-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="41590-103">Требуется сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="41590-103">Client certificate is required.</span></span> <span data-ttu-id="41590-104">В запросе не было найдено ни одного сертификата.</span><span class="sxs-lookup"><span data-stu-id="41590-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="41590-105">Описание</span><span class="sxs-lookup"><span data-stu-id="41590-105">Description</span></span>  
 <span data-ttu-id="41590-106">Эта трассировка показывает, что прослушиватель HTTPS получил запрос HTTPS, который не был связан с сертификатом клиента.</span><span class="sxs-lookup"><span data-stu-id="41590-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="41590-107">Так как прослушиватель был настроен на требование сертификатов клиента от всех запросов HTTPS, прослушивателю не удалось проверить подлинность клиента.</span><span class="sxs-lookup"><span data-stu-id="41590-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41590-108">См. также</span><span class="sxs-lookup"><span data-stu-id="41590-108">See Also</span></span>  
 [<span data-ttu-id="41590-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="41590-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="41590-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="41590-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="41590-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="41590-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
