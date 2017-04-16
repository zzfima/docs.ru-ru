---
title: "Служба AJAX без конфигурации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Служба AJAX без конфигурации
В этом примере показано использование [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для создания базовой службы асинхронных скриптов JavaScript и XML \(AJAX\) ASP.NET \(службы, которую можно использовать из клиента на основе веб\-браузера с помощью кода JavaScript\) без применения каких\-либо параметров конфигурации.  Эта служба использует особый синтаксис в файле .svc для автоматического включения конечной точки AJAX.  
  
 Поддержка технологии AJAX в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] оптимизирована для использования с ASP.NET AJAX с помощью элемента управления `ScriptManager`.  Пример использования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET AJAX см. в разделе [Ajax Samples](http://msdn.microsoft.com/ru-ru/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец сформирован на основе службы AJAX, в которой используются сообщения POST протокола HTTP.  Как описано в образце [Базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md), для размещения службы используется объект <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>.  
  
```  
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
  
```  
  
 Объект <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> автоматически добавляет конечную точку <xref:System.ServiceModel.Description.WebScriptEndpoint> к службе.  Если в конфигурацию этой конечной точки не требуется вносить изменения, то раздел \<system.ServiceModel\> из файла Web.config для этой службы может быть полностью удален.  Файл Web.config содержит некоторые параметры ASP.NET, которые используются в файле ConfigFreeClientPage.aspx.  Если дело обстоит иначе, то удалить можно весь файл Web.config.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что выполнены инструкции по настройке, приведенные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Выполните построение решения ConfigFreeAjaxService.sln, как описано в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Перейдите по адресу http:\/\/localhost\/ServiceModelSamples\/ConfigFreeClientPage.aspx \(не открывайте ConfigFreeClientPage.aspx в браузере из каталога проекта\).  
  
> [!NOTE]
>  При выполнении этого примера убедитесь, что анонимный доступ и проверка подлинности Windows не включены одновременно для папки ServiceModelSamples в IIS.  Однако если они включены, отключите проверку подлинности Windows.  По завершении выполнения примера включите проверку подлинности Windows и выполните "iisreset".  
  
## См. также  
 [Базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md)