---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: 591e1a1dcb6746d79ff5eceba7e74e890f327354
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112662"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="ae1bc-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="ae1bc-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="ae1bc-103">Заданная транзакция для заданной операции завершена в результате необработанного исключения при выполнении.</span><span class="sxs-lookup"><span data-stu-id="ae1bc-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ae1bc-104">Описание</span><span class="sxs-lookup"><span data-stu-id="ae1bc-104">Description</span></span>  
 <span data-ttu-id="ae1bc-105">Трассируется, если при попытке завершить текущую транзакцию возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="ae1bc-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="ae1bc-106">Это происходит до того, как вызвавшему объекту отправляется ответ или ошибка.</span><span class="sxs-lookup"><span data-stu-id="ae1bc-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ae1bc-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ae1bc-107">Troubleshooting</span></span>  
 <span data-ttu-id="ae1bc-108">Проверьте трассируемое сообщение на предмет наличия сообщения об исключении и других элементов, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="ae1bc-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae1bc-109">См. также</span><span class="sxs-lookup"><span data-stu-id="ae1bc-109">See also</span></span>

- [<span data-ttu-id="ae1bc-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ae1bc-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ae1bc-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ae1bc-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ae1bc-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="ae1bc-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
