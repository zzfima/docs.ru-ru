---
title: "&lt;security&gt; для &lt;ws2007HttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# &lt;security&gt; для &lt;ws2007HttpBinding&gt;
Представляет параметры безопасности, используемые с элементом [\<ws2007HttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md).  
  
## Синтаксис  
  
```  
  
<system.serviceModel>  
    <bindings>  
        <ws2007HttpBinding>  
            <binding name = "string">  
              <security mode="None/Message/Transport/TransportWithMessageCredential">  
                  <transport>  
                  </transport>  
                  <message>  
                  </message>  
              </security  
        </ws2007HttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`mode`|-   Необязательно.  Задает тип применяемого механизма обеспечения безопасности.  Значение по умолчанию — `Message`.<br /><br /> Это атрибут типа <xref:System.ServiceModel.SecurityMode>.|  
  
## Атрибут mode  
  
|Значение|Описание|  
|--------------|--------------|  
|`None`|Режим безопасности отключен.|  
|`Transport`|Безопасность обеспечивается с помощью протокола HTTPS.  Необходима настройка службы с помощью SSL\-сертификатов.  Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL\-сертификата службы.  Проверка подлинности клиента контролируется посредством атрибута `ClientCredentials` элемента [\<транспорт\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md).|  
|`Message`|Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.  По умолчанию текст сообщений SOAP шифруется и подписывается.  Этот режим предоставляет множество функций, например доступ к учетным данным службы для клиентов за пределами диапазона, выбор используемого набора алгоритмов и уровня защиты, применяемого к тексту сообщения посредством <xref:System.ServiceModel.Security.SecurityMessageProperty>.  Проверка подлинности клиента выполняется один раз для каждого сеанса, и результаты проверки сохраняются в кэше на протяжении всего сеанса.|  
|`TransportWithMessageCredential`|В данном режиме HTTPS обеспечивает целостность, конфиденциальность и проверку подлинности сервера, а механизм безопасности сообщений SOAP обеспечивает проверку подлинности клиента.  По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<транспорт\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|Определяет параметры безопасности транспорта.  Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.  Эти параметры применяются только в том случае, если режим имеет значение Transport.|  
|[\<сообщение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|Определяет параметры безопасности сообщения.  Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.  Эти параметры неприменимы, если режим имеет значение Transport.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<ws2007HttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|Привязка безопасности для приложений транспорта HTTP.|  
  
## Заметки  
 Этот элемент предназначен для взаимодействия со службами, реализующими спецификации WS\-\*.  Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS.  
  
## См. также  
 <xref:System.ServiceModel.WSHttpSecurity>   
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>   
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>   
 <xref:System.ServiceModel.BasicHttpSecurity>   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)