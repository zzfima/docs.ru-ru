---
title: "Настройка поведений клиентов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f16f32128c7223fa600802ae593d36286847dc8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="configuring-client-behaviors"></a>Настройка поведений клиентов
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] настраивает поведение двумя способами: путем ссылки на конфигурации поведения (которые определяются в разделе `<behavior>` файла конфигурации приложения) или программным образом в вызывающем приложении. В этом разделе описываются оба подхода.  
  
 При использовании файла конфигурации конфигурация поведения представляет собой именованную коллекцию параметров конфигурации. Имя каждой из конфигураций поведения должно быть уникальным. Эта строка используется в атрибуте `behaviorConfiguration` конфигурации конечной точки, чтобы связать конечную точку с поведением.  
  
## <a name="example"></a>Пример  
 В следующем фрагменте кода конфигурации определяется поведение с именем `myBehavior`. Конечная точка клиента ссылается на это поведение в атрибуте `behaviorConfiguration`.  
  
```xml  
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
  
## <a name="using-behaviors-programmatically"></a>Управление поведениями программным образом  
 Можно также настраивать или вставлять поведения программным образом путем поиска соответствующего свойства `Behaviors` в клиентском объекте [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] или в объекте клиентской фабрики каналов до того, как открыть клиент.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как программным образом вставить поведение, обратившись к свойству <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> объекта <xref:System.ServiceModel.Description.ServiceEndpoint>, возвращаемого свойством <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> до создания объекта канала.  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a>См. также  
 [\<поведения >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
