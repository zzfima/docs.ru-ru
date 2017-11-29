---
title: System.ServiceModel.MessageClosedAgain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f3963fe28ccaf55b3946254e395b770619c8f22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="38d6a-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="38d6a-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="38d6a-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="38d6a-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="38d6a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="38d6a-104">Description</span></span>  
 <span data-ttu-id="38d6a-105">Сообщение было снова закрыто.</span><span class="sxs-lookup"><span data-stu-id="38d6a-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="38d6a-106">Сообщение следует закрывать только один раз.</span><span class="sxs-lookup"><span data-stu-id="38d6a-106">A message should be closed only once.</span></span> <span data-ttu-id="38d6a-107">Если эта трассировка выдается в пользовательском коде расширения, она показывает, что пользовательский код расширения закрывает сообщение, которое уже было закрыто.</span><span class="sxs-lookup"><span data-stu-id="38d6a-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="38d6a-108">Если эта трассировка выдается посредством кода продукта, она показывает, что пользовательский код расширения может закрывать сообщение слишком рано.</span><span class="sxs-lookup"><span data-stu-id="38d6a-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d6a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="38d6a-109">See Also</span></span>  
 [<span data-ttu-id="38d6a-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="38d6a-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="38d6a-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="38d6a-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="38d6a-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="38d6a-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
