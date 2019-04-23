---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 3dd28276cd3a39497c0387f5b9d0adec23d07c37
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182199"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="64043-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="64043-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="64043-103">При закрытии подключений в этом пуле подключений возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="64043-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="64043-104">Описание</span><span class="sxs-lookup"><span data-stu-id="64043-104">Description</span></span>  
 <span data-ttu-id="64043-105">Эта трассировка уровня ошибки указывает, что произошла ошибка при закрытии пулов подключений, используемый в соединении Windows Communication Foundation (WCF), функцию пулов.</span><span class="sxs-lookup"><span data-stu-id="64043-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="64043-106">Эта ошибка может быть вызвана тем, что не удалось закрыть подключение (или набор подключений) из пула в течение времени ожидания (CloseTimeout).</span><span class="sxs-lookup"><span data-stu-id="64043-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="64043-107">При выдаче этого исключения все оставшиеся незакрытые подключения из этого пула прерываются. Незакрытые подключения из других пулов оставляются.</span><span class="sxs-lookup"><span data-stu-id="64043-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64043-108">См. также</span><span class="sxs-lookup"><span data-stu-id="64043-108">See also</span></span>

- [<span data-ttu-id="64043-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="64043-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="64043-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="64043-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="64043-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="64043-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
