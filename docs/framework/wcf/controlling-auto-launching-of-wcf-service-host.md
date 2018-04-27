---
title: Управление автозапуском узла службы WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5bb6356ba4698cad00d443fdb80b1a45d35e2175
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Управление автозапуском узла службы WCF
Можно управлять возможностью автозапуска [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] узла службы (WcfSvcHost.exe) для [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] проекта библиотеки службы при отладке другого проекта того же решения Visual Studio содержит несколько проектов.  
  
 Чтобы сделать это, щелкните правой кнопкой мыши [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] проект службы в **обозревателе решений**, выберите **свойства**и нажмите кнопку **параметры WCF** вкладки. **Запуск узла службы WCF при отладке другого проекта того же решения** флажок установлен по умолчанию. Можно снять этот флажок, чтобы узел службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] не запускался для заданного проекта при отладке другого проекта в одном решении.  
  
 Это поведение не оказывает влияние на отладку по клавише F5 или на функциональные возможности добавления ссылки на службу для этого проекта.  
  
 Эта возможность доступна в следующих проектах.  
  
-   Проект библиотеки служб [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Проект библиотеки службы последовательного рабочего процесса.  
  
-   Проект библиотеки рабочего процесса конечного автомата.  
  
-   Проект библиотеки служб синдикации.  
  
## <a name="see-also"></a>См. также  
 [Узел службы WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
