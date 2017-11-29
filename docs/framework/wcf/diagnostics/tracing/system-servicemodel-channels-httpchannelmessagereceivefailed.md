---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a258b315b5a8537de87a603b5d1ec0c18387ddbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="88626-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="88626-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>
<span data-ttu-id="88626-103">Сбой получения сообщения по каналу HTTP.</span><span class="sxs-lookup"><span data-stu-id="88626-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="88626-104">Описание</span><span class="sxs-lookup"><span data-stu-id="88626-104">Description</span></span>  
 <span data-ttu-id="88626-105">Данная трассировка может выдаваться в качестве предупреждения или ошибки.</span><span class="sxs-lookup"><span data-stu-id="88626-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="88626-106">В обоих случаях трассировка выдается, если при входящем HTTP-запросе не найден совместимый прослушиватель и HTTP-запрос получил отказ.</span><span class="sxs-lookup"><span data-stu-id="88626-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="88626-107">Это может произойти по той причине, что HTTP-команда запроса не была распознана прослушивателем HTTP, либо потому что прослушиватель ожидал передачи данных по адресу, на который был направлен запрос.</span><span class="sxs-lookup"><span data-stu-id="88626-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="88626-108">Данная трассировка выдается как предупреждение при независимом размещении и как ошибка при размещении службы в IIS.</span><span class="sxs-lookup"><span data-stu-id="88626-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88626-109">См. также</span><span class="sxs-lookup"><span data-stu-id="88626-109">See Also</span></span>  
 [<span data-ttu-id="88626-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="88626-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="88626-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="88626-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="88626-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="88626-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
