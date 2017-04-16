---
title: "Настройка поведений клиентов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Настройка поведений клиентов
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] настраивает поведение двумя способами: путем ссылки на конфигурации поведения \(которые определяются в разделе `<behavior>` файла конфигурации приложения\) или программным образом в вызывающем приложении.  В этом разделе описываются оба подхода.  
  
 При использовании файла конфигурации конфигурация поведения представляет собой именованную коллекцию параметров конфигурации.  Имя каждой из конфигураций поведения должно быть уникальным.  Эта строка используется в атрибуте `behaviorConfiguration` конфигурации конечной точки, чтобы связать конечную точку с поведением.  
  
## Пример  
 В следующем фрагменте кода конфигурации определяется поведение с именем `myBehavior`.  Конечная точка клиента ссылается на это поведение в атрибуте `behaviorConfiguration`.  
  
```  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## Управление поведениями программным образом  
 Можно также настраивать или вставлять поведения программным образом путем поиска соответствующего свойства `Behaviors` в клиентском объекте [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] или в объекте клиентской фабрики каналов до того, как открыть клиент.  
  
## Пример  
 В следующем примере кода показано, как программным образом вставить поведение, обратившись к свойству <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> объекта <xref:System.ServiceModel.Description.ServiceEndpoint>, возвращаемого свойством <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> до создания объекта канала.  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## См. также  
 [\<поведения\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)