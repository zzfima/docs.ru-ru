---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 3dd28276cd3a39497c0387f5b9d0adec23d07c37
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182199"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="2b3c5-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="2b3c5-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="2b3c5-103">При закрытии подключений в этом пуле подключений возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2b3c5-104">Описание</span><span class="sxs-lookup"><span data-stu-id="2b3c5-104">Description</span></span>  
 <span data-ttu-id="2b3c5-105">Эта трассировка уровня ошибки указывает, что произошла ошибка при закрытии пулов подключений, используемый в соединении Windows Communication Foundation (WCF), функцию пулов.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="2b3c5-106">Эта ошибка может быть вызвана тем, что не удалось закрыть подключение (или набор подключений) из пула в течение времени ожидания (CloseTimeout).</span><span class="sxs-lookup"><span data-stu-id="2b3c5-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="2b3c5-107">При выдаче этого исключения все оставшиеся незакрытые подключения из этого пула прерываются. Незакрытые подключения из других пулов оставляются.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b3c5-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2b3c5-108">See also</span></span>

- [<span data-ttu-id="2b3c5-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="2b3c5-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="2b3c5-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="2b3c5-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2b3c5-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="2b3c5-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
