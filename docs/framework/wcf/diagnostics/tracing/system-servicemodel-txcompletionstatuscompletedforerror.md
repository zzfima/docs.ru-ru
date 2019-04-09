---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: 591e1a1dcb6746d79ff5eceba7e74e890f327354
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112662"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="22782-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="22782-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="22782-103">Заданная транзакция для заданной операции завершена в результате необработанного исключения при выполнении.</span><span class="sxs-lookup"><span data-stu-id="22782-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="22782-104">Описание</span><span class="sxs-lookup"><span data-stu-id="22782-104">Description</span></span>  
 <span data-ttu-id="22782-105">Трассируется, если при попытке завершить текущую транзакцию возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="22782-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="22782-106">Это происходит до того, как вызвавшему объекту отправляется ответ или ошибка.</span><span class="sxs-lookup"><span data-stu-id="22782-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="22782-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="22782-107">Troubleshooting</span></span>  
 <span data-ttu-id="22782-108">Проверьте трассируемое сообщение на предмет наличия сообщения об исключении и других элементов, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="22782-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22782-109">См. также</span><span class="sxs-lookup"><span data-stu-id="22782-109">See also</span></span>

- [<span data-ttu-id="22782-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="22782-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="22782-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="22782-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="22782-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="22782-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
