---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: 3a73834888ae4a8945bd71492d787e23868fa5e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33480747"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="fd4a4-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="fd4a4-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="fd4a4-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="fd4a4-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="fd4a4-104">Описание</span><span class="sxs-lookup"><span data-stu-id="fd4a4-104">Description</span></span>  
 <span data-ttu-id="fd4a4-105">Сообщение было снова закрыто.</span><span class="sxs-lookup"><span data-stu-id="fd4a4-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="fd4a4-106">Сообщение следует закрывать только один раз.</span><span class="sxs-lookup"><span data-stu-id="fd4a4-106">A message should be closed only once.</span></span> <span data-ttu-id="fd4a4-107">Если эта трассировка выдается в пользовательском коде расширения, она показывает, что пользовательский код расширения закрывает сообщение, которое уже было закрыто.</span><span class="sxs-lookup"><span data-stu-id="fd4a4-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="fd4a4-108">Если эта трассировка выдается посредством кода продукта, она показывает, что пользовательский код расширения может закрывать сообщение слишком рано.</span><span class="sxs-lookup"><span data-stu-id="fd4a4-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4a4-109">См. также</span><span class="sxs-lookup"><span data-stu-id="fd4a4-109">See Also</span></span>  
 [<span data-ttu-id="fd4a4-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="fd4a4-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="fd4a4-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="fd4a4-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="fd4a4-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="fd4a4-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
