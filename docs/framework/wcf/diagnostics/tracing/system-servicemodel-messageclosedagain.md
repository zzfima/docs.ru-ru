---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a18355d55359df665d0e936ce95da34bf07aec6a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181356"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="fdac6-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="fdac6-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="fdac6-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="fdac6-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="fdac6-104">Описание</span><span class="sxs-lookup"><span data-stu-id="fdac6-104">Description</span></span>  
 <span data-ttu-id="fdac6-105">Сообщение было снова закрыто.</span><span class="sxs-lookup"><span data-stu-id="fdac6-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="fdac6-106">Сообщение следует закрывать только один раз.</span><span class="sxs-lookup"><span data-stu-id="fdac6-106">A message should be closed only once.</span></span> <span data-ttu-id="fdac6-107">Если эта трассировка выдается в пользовательском коде расширения, она показывает, что пользовательский код расширения закрывает сообщение, которое уже было закрыто.</span><span class="sxs-lookup"><span data-stu-id="fdac6-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="fdac6-108">Если эта трассировка выдается посредством кода продукта, она показывает, что пользовательский код расширения может закрывать сообщение слишком рано.</span><span class="sxs-lookup"><span data-stu-id="fdac6-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdac6-109">См. также</span><span class="sxs-lookup"><span data-stu-id="fdac6-109">See also</span></span>

- [<span data-ttu-id="fdac6-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="fdac6-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="fdac6-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="fdac6-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="fdac6-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="fdac6-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
