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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1808015cd310e64ac05e9827a229112ddd76a80f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="6bcdd-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="6bcdd-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="6bcdd-103">Требуется сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="6bcdd-103">Client certificate is required.</span></span> <span data-ttu-id="6bcdd-104">В запросе не было найдено ни одного сертификата.</span><span class="sxs-lookup"><span data-stu-id="6bcdd-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6bcdd-105">Описание</span><span class="sxs-lookup"><span data-stu-id="6bcdd-105">Description</span></span>  
 <span data-ttu-id="6bcdd-106">Эта трассировка показывает, что прослушиватель HTTPS получил запрос HTTPS, который не был связан с сертификатом клиента.</span><span class="sxs-lookup"><span data-stu-id="6bcdd-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="6bcdd-107">Так как прослушиватель был настроен на требование сертификатов клиента от всех запросов HTTPS, прослушивателю не удалось проверить подлинность клиента.</span><span class="sxs-lookup"><span data-stu-id="6bcdd-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bcdd-108">См. также</span><span class="sxs-lookup"><span data-stu-id="6bcdd-108">See Also</span></span>  
 [<span data-ttu-id="6bcdd-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="6bcdd-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="6bcdd-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="6bcdd-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="6bcdd-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="6bcdd-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
