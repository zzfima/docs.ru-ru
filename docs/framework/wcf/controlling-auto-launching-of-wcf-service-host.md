---
title: "Управление автозапуском узла службы WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 65daceac9b865f3e8224c709d672344606905d9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Управление автозапуском узла службы WCF
Можно управлять возможностью автозапуска узла службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] (WcfSvcHost.exe) для проекта библиотеки службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] при отладке другого проекта в одном решении [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], которое содержит несколько проектов.  
  
 Чтобы сделать это, щелкните правой кнопкой мыши [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] проект службы в **обозревателе решений**, выберите **свойства**и нажмите кнопку **параметры WCF** вкладки. **Запуск узла службы WCF при отладке другого проекта того же решения** флажок установлен по умолчанию. Можно снять этот флажок, чтобы узел службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] не запускался для заданного проекта при отладке другого проекта в одном решении.  
  
 Это поведение не оказывает влияние на отладку по клавише F5 или на функциональные возможности добавления ссылки на службу для этого проекта.  
  
 Эта возможность доступна в следующих проектах.  
  
-   Проект библиотеки служб [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Проект библиотеки службы последовательного рабочего процесса.  
  
-   Проект библиотеки рабочего процесса конечного автомата.  
  
-   Проект библиотеки служб синдикации.  
  
## <a name="see-also"></a>См. также  
 [Узел службы WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
