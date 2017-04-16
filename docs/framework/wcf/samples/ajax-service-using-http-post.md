---
title: "Служба AJAX с использованием HTTP POST | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# Служба AJAX с использованием HTTP POST
В этом примере показано, как с помощью [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] создать службу [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] асинхронных скриптов JavaScript и XML \(AJAX\), использующую HTTP\-метод POST. Обращаться к службе AJAX можно с использованием кода JavaScript из клиента на основе веб\-браузера. Этот пример основан на примере [Базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md); единственное различие между двумя примерами состоит в использовании HTTP\-метода POST вместо HTTP\-метода GET.  
  
 Поддержка технологии AJAX в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] оптимизирована для использования с ASP.NET AJAX с помощью элемента управления `ScriptManager`. Пример использования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET AJAX см. в разделе [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Служба в следующем примере является службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] без кода, относящегося к AJAX.  
  
 Если к операции применяется атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> или не применяется атрибут <xref:System.ServiceModel.Web.WebGetAttribute>, используется HTTP\-метод по умолчанию \(POST\). Запросы POST строить тяжелее, чем запросы GET, однако они не кэшируются; запросы POST следует использовать для всех операций, в которых нельзя использовать кэширование.  
  
```  
[ServiceContract(Namespace = "PostAjaxService")]  
    public interface ICalculator  
    {        [WebInvoke]  
        double Add(double n1, double n2);  
        //Other operations omitted…  
    }  
  
```  
  
 Создайте конечную точку AJAX в службе с помощью <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> точно так же, как в образце базовой службы AJAX.  
  
 В отличие от запросов GET вызывать службы POST из браузера нельзя. Например, переход по адресу "http:\/\/localhost\/ServiceModelSamples\/service.svc\/Add?n1\=100&n2\=200" приведет к ошибке, поскольку служба POST ожидает передачи параметров `n1` и `n2` в тексте сообщения \(в формате JSON\), а не в URL\-адресе.  
  
 Клиентская веб\-страница PostAjaxClientPage.aspx содержит код ASP.NET для вызова службы, когда пользователь нажимает одну из кнопок операций на странице. Служба отвечает так же, как и в образце [Базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) с запросом GET.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [примеров Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) и скачайте все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что выполнены инструкции по настройке, приведенные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Выполните построение решения PostAjaxService.sln, как описано в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Перейдите к странице http:\/\/localhost\/ServiceModelSamples\/PostAjaxClientPage.aspx \(не открывайте страницу PostAjaxClientPage.aspx в браузере из каталога проекта\).  
  
## См. также