---
title: "Как установить максимальную разницу в показаниях часов | Microsoft Docs"
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
  - "свойство MaxClockSkew"
  - "WCF, пользовательские привязки"
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Как установить максимальную разницу в показаниях часов
Если настройки времени на двух компьютерах различаются, возможен сбой критичных по времени функций.  Чтобы устранить такую вероятность, задайте для свойства `MaxClockSkew` значение <xref:System.TimeSpan>.  Это свойство предусмотрено в двух классах.  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
>  Важно.   Для безопасного диалога изменения свойства `MaxClockSkew` должны производиться на этапе начальной загрузки службы или клиента.  Чтобы это сделать, необходимо задать данное свойство в <xref:System.ServiceModel.Channels.SecurityBindingElement>, возвращаемом <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>.  
  
 Чтобы изменить это свойство в одной из привязок, предоставляемых системой, необходимо найти элемент привязки безопасности в коллекции привязок и задать для свойства `MaxClockSkew` новое значение.  От класса <xref:System.ServiceModel.Channels.SecurityBindingElement> наследуют два класса: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.  При извлечении привязки безопасности из коллекции необходимо приведение к одному из этих типов, чтобы правильно задать свойство `MaxClockSkew`.  В следующем примере используется привязка <xref:System.ServiceModel.WSHttpBinding>, которая использует класс <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  Список с указанием, какой тип привязки безопасности следует использовать в каждой привязке, предоставляемой системой, см. в разделе [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
### Создание пользовательской привязки с новым значением разницы в показаниях часов в коде  
  
1.  > [!WARNING]
    >  Примечание.   Добавьте в код ссылки на следующие пространства имен: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions> и <xref:System.ServiceModel.Security.Tokens>.  
  
     Создайте новый экземпляр класса <xref:System.ServiceModel.WSHttpBinding> и задайте для него режим безопасности <xref:System.ServiceModel.SecurityMode>.  
  
2.  Создайте новый экземпляр класса <xref:System.ServiceModel.Channels.BindingElementCollection>, вызвав метод <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.  
  
3.  С помощью метода <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> класса <xref:System.ServiceModel.Channels.BindingElementCollection> найдите требуемый элемент привязки безопасности.  
  
4.  При использовании метода <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> выполните приведение к фактическому типу.  В приведенном ниже примере производится приведение к типу <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
5.  Задайте свойство <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> в элементе привязки безопасности.  
  
6.  Создайте <xref:System.ServiceModel.ServiceHost> с требуемыми типом и базовым адресом службы.  
  
7.  С помощью метода <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> добавьте конечную точку и включите <xref:System.ServiceModel.Channels.CustomBinding>.  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
### Задание MaxClockSkew в конфигурации  
  
1.  Создайте [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) в разделе элементов [\<привязки\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md).  
  
2.  Создайте элемент [\<привязка\>](../../../../docs/framework/misc/binding.md) и присвойте атрибуту `name` соответствующее значение.  В следующем примере задается значение `MaxClockSkewBinding`.  
  
3.  Добавьте элемент кодирования.  Приведенный ниже пример добавляет [\<textMessageEncoding\>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
4.  Добавьте элемент [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) и задайте требуемое значение атрибута `authenticationMode`.  В следующем примере для этого атрибута задается значение `Kerberos`, чтобы указать, что в службе используется проверка подлинности Windows.  
  
5.  Добавьте [\<localServiceSettings\>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) и задайте для атрибута `maxClockSkew` значение в виде `"##:##:##"`.  В следующем примере задается значение 7 минут.  При необходимости добавьте [\<localServiceSettings\>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) и задайте для атрибута `maxClockSkew` соответствующее значение.  
  
6.  Добавьте транспортный элемент.  В следующем примере используется [\<httpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
7.  Для безопасного диалога параметры безопасности должны задаваться при начальной загрузке в элементе [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md).  
  
    ```  
  
    <bindings>  
      <customBinding>  
        <binding name="MaxClockSkewBinding">  
            <textMessageEncoding />  
            <security authenticationMode="Kerberos">  
               <localClientSettings maxClockSkew="00:07:00" />  
               <localServiceSettings maxClockSkew="00:07:00" />  
               <secureConversationBootstrap>  
                  <localClientSettings maxClockSkew="00:30:00" />  
                  <localServiceSettings maxClockSkew="00:30:00" />  
               </secureConversationBootstrap>  
            </security>  
            <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
  
    ```  
  
## См. также  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>   
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)