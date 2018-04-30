---
title: Размещение в службах IIS
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b933626c2f3f5ee7121d141d3704376efeb54ba5
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="hosting-in-internet-information-services"></a>Размещение в службах IIS
Один из вариантов размещения служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - внутри приложения IIS. Эта модель размещения похожа на модель, используемую [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и веб-службами ASP.NET (ASMX).  
  
## <a name="versions-of-iis"></a>Версии IIS  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно размещать в следующий версиях IIS в следующих операционных системах.  
  
-   IIS 5.1 в [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]. Эта среда хорошо подходит для проектирования и разработки размещаемых в IIS приложений, которые впоследствии будут развертываться на серверных операционных системах, например на [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
-   [!INCLUDE[iis601](../../../../includes/iis601-md.md)] в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. В службах [!INCLUDE[iis601](../../../../includes/iis601-md.md)] реализована расширенная модель процессов, которая обеспечивает лучшую масштабируемость, надежность и изоляцию приложений. Эта среда подходит для развертывания служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], использующих только транспорт HTTP, в рабочей среде.  
  
-   IIS 7.0 в [!INCLUDE[wv](../../../../includes/wv-md.md)] и [!INCLUDE[lserver](../../../../includes/lserver-md.md)]. Службы IIS 7.0 реализуют такую же расширенную модель процессов, как и [!INCLUDE[iis601](../../../../includes/iis601-md.md)], но используют службу активации Windows (WAS) для обеспечения поддержки активации и сетевого взаимодействия с помощью протоколов, отличных от HTTP. Эта среда подходит для разработки служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которые взаимодействуют с помощью любых сетевых протоколов, поддерживаемых [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (включая HTTP, net.tcp, net.pipe и net.msmq). Дополнительные сведения об АКТИВАЦИИ см. в разделе [размещение в службе активации процессов Windows](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
-   [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496) работает с [!INCLUDE[iisver](../../../../includes/iisver-md.md)] и активации процессов Windows Service (WAS) для предоставления полнофункциональных приложений размещения среды для служб NET4 WCF и WF. К ее преимуществам относятся управление жизненным циклом, перезапуск процессов, совместное размещение, быстрая защита от сбоев, обработка потерянных процессов, активация по запросу и наблюдение за работоспособностью. Дополнительные сведения см. в разделе [функции размещения AppFabric](http://go.microsoft.com/fwlink/?LinkId=196494) и [размещения AppFabric](http://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="benefits-of-iis-hosting"></a>Преимущества размещения в IIS  
 Размещение служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в IIS имеет несколько преимуществ:  
  
-   службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещаемые в IIS, развертываются и управляются, как и приложения IIS других типов, включая приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и ASMX;  
  
-   службы IIS предоставляют функции активации процессов, управления работоспособностью и перезапуска процессов, что позволяет повысить надежность приложений;  
  
-   как и [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещенные в [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], могут использовать преимущества модели совместного размещения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], когда несколько приложений располагаются в одном рабочем процессе в целях повышения масштабируемости и эффективности использования ресурсов сервера;  
  
-   службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещаемые в IIS, используют ту же модель динамической компиляции, что и [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)], что упрощает разработку и развертывание размещенных служб.  
  
 При принятии решения о размещении служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в IIS важно помнить, что в версиях IIS 5.1 и [!INCLUDE[iis601](../../../../includes/iis601-md.md)] можно использовать для взаимодействия только протокол HTTP. Дополнительные сведения о выборе среды размещения см. в разделе [размещение служб](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>Развертывание службы WCF, размещаемой в IIS  
 Процесс разработки и развертывания службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещаемой в IIS, состоит из следующих задач.  
  
-   Проверка правильности установки и регистрации служб IIS, ASP, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и компонента активации HTTP [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Создание нового приложения IIS или повторное использование существующего приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
-   Создание SVC-файла для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
-   Развертывание реализации службы в приложение IIS.  
  
-   Настройка службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
 Описание каждого из этих задач см. в разделе [развертывание службы WCF, Internet Information Services-Hosted](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="wcf-services-and-aspnet"></a>Службы WCF и ASP.NET  
 Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно размещать параллельно с [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] или в режиме совместимости [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], в котором службы могут использовать все функции платформы веб-приложений [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Описание этих возможностей см. в разделе [службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
## <a name="see-also"></a>См. также  
 [Расширение размещения с использованием ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 [Развертывание службы WCF, размещенной в IIS](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)  
 [Службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [Рекомендации по размещению в службах IIS](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Настройка IIS 7.0 для Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)  
 [Функции размещения Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
