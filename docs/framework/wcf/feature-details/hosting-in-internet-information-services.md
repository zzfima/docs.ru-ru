---
title: Размещение в службах IIS
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 588e069280afc369256fdbee0132f732348ffc37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-in-internet-information-services"></a>Размещение в службах IIS
Один из вариантов размещения служб Windows Communication Foundation (WCF)-внутри приложения Internet Information Services (IIS). Эта модель размещения похожа на модель, используемую [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и веб-службами ASP.NET (ASMX).  
  
## <a name="versions-of-iis"></a>Версии IIS  
 WCF можно размещать в следующий версиях IIS в следующих операционных системах.  
  
-   IIS 5.1 в [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]. Эта среда хорошо подходит для проектирования и разработки размещаемых в IIS приложений, которые впоследствии будут развертываться на серверных операционных системах, например на [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
-   [!INCLUDE[iis601](../../../../includes/iis601-md.md)] в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. В службах [!INCLUDE[iis601](../../../../includes/iis601-md.md)] реализована расширенная модель процессов, которая обеспечивает лучшую масштабируемость, надежность и изоляцию приложений. Эта среда подходит для рабочего развертывания служб WCF, использующих только транспорт HTTP.  
  
-   IIS 7.0 в [!INCLUDE[wv](../../../../includes/wv-md.md)] и [!INCLUDE[lserver](../../../../includes/lserver-md.md)]. Службы IIS 7.0 реализуют такую же расширенную модель процессов, как и [!INCLUDE[iis601](../../../../includes/iis601-md.md)], но используют службу активации Windows (WAS) для обеспечения поддержки активации и сетевого взаимодействия с помощью протоколов, отличных от HTTP. Эта среда подходит для разработки служб WCF, взаимодействующих с использованием любого сетевого протокола, поддерживаемого службами WCF (включая HTTP, net.tcp, net.pipe и net.msmq). Дополнительные сведения об АКТИВАЦИИ см. в разделе [размещение в службе активации процессов Windows](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
-   [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496) работает с [!INCLUDE[iisver](../../../../includes/iisver-md.md)] и активации процессов Windows Service (WAS) для предоставления полнофункциональных приложений размещения среды для служб NET4 WCF и WF. К ее преимуществам относятся управление жизненным циклом, перезапуск процессов, совместное размещение, быстрая защита от сбоев, обработка потерянных процессов, активация по запросу и наблюдение за работоспособностью. Дополнительные сведения см. в разделе [функции размещения AppFabric](http://go.microsoft.com/fwlink/?LinkId=196494) и [размещения AppFabric](http://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="benefits-of-iis-hosting"></a>Преимущества размещения в IIS  
 Размещение служб WCF в IIS имеет несколько преимуществ:  
  
-   Службы WCF, размещенные в IIS, развертываются и управляются как любой другой тип приложения IIS, включая [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] приложений и ASMX.  
  
-   службы IIS предоставляют функции активации процессов, управления работоспособностью и перезапуска процессов, что позволяет повысить надежность приложений;  
  
-   Как [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], службы WCF, размещенные в [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] могут воспользоваться преимуществами [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] модели совместного размещения, где несколько приложений располагаются в общем рабочем процессе плотность улучшенные сервера и масштабируемости.  
  
-   Службы WCF, размещенные в IIS используют одну и ту же модель динамической компиляции как [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)], что упрощает разработку и развертывание размещенных служб.  
  
 При принятии решения о размещении служб WCF в IIS, важно помнить, IIS 5.1 и [!INCLUDE[iis601](../../../../includes/iis601-md.md)] ограничена связью только по протоколу HTTP. Дополнительные сведения о выборе среды размещения см. в разделе [размещение служб](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>Развертывание службы WCF, размещаемой в IIS  
 Разработка и развертывание службы WCF, размещенных в IIS состоит из следующих задач:  
  
-   Убедитесь, что службы IIS, ASP.NET, WCF и компонента активации WCF HTTP службы правильно установлен и зарегистрирован.  
  
-   Создание нового приложения IIS или повторное использование существующего приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] .  
  
-   Создание SVC-файла для службы WCF.  
  
-   Развертывание реализации службы в приложение IIS.  
  
-   Настройка службы WCF.  
  
 Описание каждого из этих задач см. в разделе [развертывание службы WCF, Internet Information Services-Hosted](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="wcf-services-and-aspnet"></a>Службы WCF и ASP.NET  
 Службы WCF может быть размещена либо side-by-side с [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] или в [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] режим совместимости, в котором службы могут использовать все преимущества, обеспечиваемые [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] платформы веб-приложений. Описание этих возможностей см. в разделе [службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
## <a name="see-also"></a>См. также  
 [Расширение размещения с использованием ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 [Развертывание службы WCF, размещенной в IIS](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)  
 [Службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [Рекомендации по размещению в службах IIS](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Настройка IIS 7.0 для Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)  
 [Функции размещения Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
