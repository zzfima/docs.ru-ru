---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: e36126dcdfcc87a410d200cdf23aac670dc2b5e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596516"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="7d4ee-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="7d4ee-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="7d4ee-103">Заданная транзакция для заданной операции завершена в результате необработанного исключения при выполнении.</span><span class="sxs-lookup"><span data-stu-id="7d4ee-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7d4ee-104">Описание</span><span class="sxs-lookup"><span data-stu-id="7d4ee-104">Description</span></span>  
 <span data-ttu-id="7d4ee-105">Трассируется, если при попытке завершить текущую транзакцию возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="7d4ee-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="7d4ee-106">Это происходит до того, как вызвавшему объекту отправляется ответ или ошибка.</span><span class="sxs-lookup"><span data-stu-id="7d4ee-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="7d4ee-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="7d4ee-107">Troubleshooting</span></span>  
 <span data-ttu-id="7d4ee-108">Проверьте трассируемое сообщение на предмет наличия сообщения об исключении и других элементов, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="7d4ee-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d4ee-109">См. также</span><span class="sxs-lookup"><span data-stu-id="7d4ee-109">See also</span></span>
- [<span data-ttu-id="7d4ee-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="7d4ee-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="7d4ee-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="7d4ee-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7d4ee-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="7d4ee-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
