---
title: "Перенос приложений удаленного взаимодействия .NET на платформу WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 240901f4fa04a2468d5964821680506ea117bf7f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="abbb3-102">Перенос приложений удаленного взаимодействия .NET на платформу WCF</span><span class="sxs-lookup"><span data-stu-id="abbb3-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="abbb3-103">**Этот раздел относится к технологии прежних версий, которая сохраняется для обеспечения обратной совместимости с существующими приложениями и не рекомендуется для разработки новых приложений. Теперь распределенные приложения разрабатываются при помощи платформы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**</span><span class="sxs-lookup"><span data-stu-id="abbb3-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**</span></span>  
  
 <span data-ttu-id="abbb3-104">Существует два способа использовать преимущества [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в сочетании с существующими приложениями удаленного взаимодействия .NET: интеграция и миграция.</span><span class="sxs-lookup"><span data-stu-id="abbb3-104">There are two ways to take advantage of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="abbb3-105">Интеграция позволяет запускать .Net Remoting 2.0 и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] параллельно, т. е. предоставлять одни и те же бизнес-объекты одновременно посредством обеих технологий без внесения изменений в существующий код .Net Remoting 2.0.</span><span class="sxs-lookup"><span data-stu-id="abbb3-105">Integration allows you to have .Net Remoting 2.0 and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .Net Remoting 2.0 code.</span></span> <span data-ttu-id="abbb3-106">Интеграция требует использования [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 или выше.</span><span class="sxs-lookup"><span data-stu-id="abbb3-106">Integration requires that you are running on [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 or greater.</span></span> <span data-ttu-id="abbb3-107">Если совместимость на уровне линий связи с системами Remoting 2.0 не требуется, для использования преимуществ [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно целиком мигрировать службу в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="abbb3-107">If you want to take advantage of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="abbb3-108">Миграция с .NET Remoting 2.0 на [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требует внесения изменений в интерфейс удаленного объекта и параметры его конфигурации.</span><span class="sxs-lookup"><span data-stu-id="abbb3-108">Migration from .NET Remoting 2.0 to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="abbb3-109">В этих разделах рассматриваются [из удаленного взаимодействия на платформу Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).</span><span class="sxs-lookup"><span data-stu-id="abbb3-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abbb3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="abbb3-110">See Also</span></span>  
 [<span data-ttu-id="abbb3-111">Концептуальный обзор</span><span class="sxs-lookup"><span data-stu-id="abbb3-111">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
