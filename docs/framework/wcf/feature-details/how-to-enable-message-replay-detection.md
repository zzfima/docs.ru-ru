---
title: "Как включить обнаружение повтора сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "обнаружение воспроизведения [WCF]"
  - "безопасность WCF"
  - "WCF, пользовательские привязки"
  - "WCF, безопасность"
ms.assetid: 8b847e91-69a3-49e1-9e5f-0c455e50d804
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Как включить обнаружение повтора сообщений
Атака воспроизведения заключается в том, что злоумышленник копирует поток сообщений между двумя сторонами и воспроизводит его для одной или нескольких сторон.Если не приняты ответные меры, атакованные компьютеры обрабатывают этот поток как надлежащие сообщения, что приводит к ряду негативных последствий, таких как повторные заказы одного элемента.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] об обнаружении воспроизведения сообщений см. в разделе [Обнаружение воспроизведения сообщений](http://go.microsoft.com/fwlink/?LinkId=88536).  
  
 В следующей процедуре показаны различные свойства, с помощью которых можно управлять обнаружением воспроизведения, используя [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
### Управление обнаружением воспроизведения на стороне клиента с помощью кода  
  
1.  Создайте элемент <xref:System.ServiceModel.Channels.SecurityBindingElement> для использования в привязке <xref:System.ServiceModel.Channels.CustomBinding>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).В следующем примере используется объект <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, созданный с помощью объекта <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> класса <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
2.  С помощью свойства <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> получите ссылку на класс <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> и задайте некоторые из следующих свойств согласно необходимости:  
  
    1.  `DetectReplay`.Логическое значение.Управляет тем, пытается ли клиент обнаружить воспроизведение сообщений сервера.Значение по умолчанию — `true`.  
  
    2.  `MaxClockSkew`.Значение <xref:System.TimeSpan>.Задает максимальную разницу по времени, допускаемую механизмом обнаружения воспроизведения между клиентом и сервером.Механизм безопасности проверяет отправленную отметку времени и определяет, не слишком ли давно она отправлена.Значение по умолчанию — 5 минут.  
  
    3.  `ReplayWindow`.Значение `TimeSpan`.Задает максимальное время жизни сообщения в сети с момента его отправки сервером \(через промежуточные узлы\), прежде чем оно доставляется клиенту.Клиент отслеживает подписи сообщений, отправленных в течение последнего промежутка времени `ReplayWindow`, с целью обнаружения воспроизведения.  
  
    4.  `ReplayCacheSize`.Целочисленное значение.Клиент сохраняет подписи сообщений в кэше.Этот параметр задает максимальное количество подписей, которое может храниться в кэше.Если количество сообщений, отправленных в пределах последнего окна воспроизведения, достигает предела кэша, новые сообщения отклоняются, пока не будет достигнут предел по времени для самых старых подписей в кэше.Значение по умолчанию — 500000.  
  
### Управление обнаружением воспроизведения на стороне службы с помощью кода  
  
1.  Создайте элемент <xref:System.ServiceModel.Channels.SecurityBindingElement> для использования в привязке <xref:System.ServiceModel.Channels.CustomBinding>.  
  
2.  С помощью свойства <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> получите ссылку на класс <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> и задайте свойства, как указано выше.  
  
### Управление обнаружением воспроизведения с помощью конфигурации для клиента или службы  
  
1.  Создайте привязку [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
2.  Создайте элемент `<security>`.  
  
3.  Создайте [\<localClientSettings\>](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md) или [\<localServiceSettings\>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md).  
  
4.  Задайте следующие значение атрибутов \(согласно необходимости\): `detectReplays`, `maxClockSkew`, `replayWindow` и `replayCacheSize`.В следующем примере задаются атрибуты для обоих элементов: `<localServiceSettings>``<localClientSettings> и` .  
  
    ```  
    <customBinding>  
      <binding name="NewBinding0">  
       <textMessageEncoding />  
        <security>  
         <localClientSettings   
          replayCacheSize="800000"   
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
         <localServiceSettings   
          replayCacheSize="800000"   
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
        <secureConversationBootstrap />  
       </security>  
      <httpTransport />  
     </binding>  
    </customBinding>  
    ```  
  
## Пример  
 В следующем примере создается элемент <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> с помощью метода <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A>.  
  
 [!code-csharp[c_ReplayDetection#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_replaydetection/cs/source.cs#1)]
 [!code-vb[c_ReplayDetection#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_replaydetection/vb/source.vb#1)]  
  
## Область воспроизведения: только для режима безопасности сообщений  
 Обратите внимание, что следующие процедуры применяются только для режима безопасности сообщений.В режиме транспорта и в режиме транспорта с учетными данными сообщения воспроизведение обнаруживает транспортный механизм.  
  
## Примечания о безопасном диалоге  
 Для привязок, обеспечивающих безопасные диалоги, можно изменить эти настройки и для канала приложения, и для привязки начальной загрузки безопасного диалога.Например, можно отключить воспроизведение для канала приложения, но разрешить его для канала начальной загрузки, устанавливающего безопасный диалог.  
  
 Если сеансы безопасных диалогов не используются, средства обнаружения воспроизведения не гарантируют обнаружение воспроизведения в случаях использования фермы серверов и перезапуска процесса.Это относится к следующим привязкам, предоставляемым системой:  
  
-   <xref:System.ServiceModel.BasicHttpBinding>.  
  
-   Привязка <xref:System.ServiceModel.WSHttpBinding>, свойству <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> которой установлено значение `false`.  
  
## Компиляция кода  
  
-   Для компиляции кода требуются следующие пространства имен.  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
## См. также  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>   
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>   
 [Безопасные диалоги и безопасные сеансы](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)   
 [\<localClientSettings\>](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md)   
 [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)