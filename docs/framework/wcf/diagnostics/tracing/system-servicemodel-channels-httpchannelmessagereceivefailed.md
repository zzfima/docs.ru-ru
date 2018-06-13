---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: f79f5703c621951029f3e7f6a36a3d0ebeca58a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33477455"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="f0b9a-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="f0b9a-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>
<span data-ttu-id="f0b9a-103">Сбой получения сообщения по каналу HTTP.</span><span class="sxs-lookup"><span data-stu-id="f0b9a-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f0b9a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="f0b9a-104">Description</span></span>  
 <span data-ttu-id="f0b9a-105">Данная трассировка может выдаваться в качестве предупреждения или ошибки.</span><span class="sxs-lookup"><span data-stu-id="f0b9a-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="f0b9a-106">В обоих случаях трассировка выдается, если при входящем HTTP-запросе не найден совместимый прослушиватель и HTTP-запрос получил отказ.</span><span class="sxs-lookup"><span data-stu-id="f0b9a-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="f0b9a-107">Это может произойти по той причине, что HTTP-команда запроса не была распознана прослушивателем HTTP, либо потому что прослушиватель ожидал передачи данных по адресу, на который был направлен запрос.</span><span class="sxs-lookup"><span data-stu-id="f0b9a-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="f0b9a-108">Данная трассировка выдается как предупреждение при независимом размещении и как ошибка при размещении службы в IIS.</span><span class="sxs-lookup"><span data-stu-id="f0b9a-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b9a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="f0b9a-109">See Also</span></span>  
 [<span data-ttu-id="f0b9a-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="f0b9a-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f0b9a-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="f0b9a-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f0b9a-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="f0b9a-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
