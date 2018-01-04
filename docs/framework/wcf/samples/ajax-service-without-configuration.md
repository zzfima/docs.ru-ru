---
title: "Служба AJAX без конфигурации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 82d9bb27ef20aa4e425e232a23c785af3b7e6e5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ajax-service-without-configuration"></a>Служба AJAX без конфигурации
В этом примере показано использование [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для создания базовой службы асинхронных скриптов JavaScript и XML (AJAX) ASP.NET (службы, которую можно использовать из клиента на основе веб-браузера с помощью кода JavaScript) без применения каких-либо параметров конфигурации. Эта служба использует особый синтаксис в файле .svc для автоматического включения конечной точки AJAX.  
  
 Поддержка технологии AJAX в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] оптимизирована для использования с ASP.NET AJAX с помощью элемента управления `ScriptManager`. Пример использования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET AJAX, в разделе [примеров Ajax](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец сформирован на основе службы AJAX, в которой используются сообщения POST протокола HTTP. Как описано в [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образце <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> используется для размещения службы.  
  
```  
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```  
  
 Объект <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> автоматически добавляет конечную точку <xref:System.ServiceModel.Description.WebScriptEndpoint> к службе. Если необходимо сделать для конечной точки, без изменения конфигурации \<системы. ServiceModel > можно полностью удалить раздел из файла Web.config для службы. Файл Web.config содержит некоторые параметры ASP.NET, которые используются в файле ConfigFreeClientPage.aspx. Если дело обстоит иначе, то удалить можно весь файл Web.config.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что настройка инструкциям [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Постройте решение ConfigFreeAjaxService.sln, как описано в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Перейдите по адресу http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx (не открывайте ConfigFreeClientPage.aspx в браузере из каталога проекта).  
  
> [!NOTE]
>  При выполнении этого примера убедитесь, что анонимный доступ и проверка подлинности Windows не включены одновременно для папки ServiceModelSamples в IIS. Однако если они включены, отключите проверку подлинности Windows. По завершении выполнения примера включите проверку подлинности Windows и выполните "iisreset".  
  
## <a name="see-also"></a>См. также  
 [Базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
