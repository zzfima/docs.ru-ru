---
title: Настройка поведений клиентов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: bf65844cda195847989d1eb8ef752fe87c9de22c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532205"
---
# <a name="configuring-client-behaviors"></a>Настройка поведений клиентов
Windows Communication Foundation (WCF) настраивает поведение двумя способами: путем ссылки на конфигурации поведения, которые определены в `<behavior>` разделе в файле конфигурации клиентского приложения — либо программным способом в вызывающем объекте приложение. В этом разделе описываются оба подхода.  
  
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
 Можно также настраивать или вставлять поведения программным образом путем поиска соответствующего `Behaviors` свойства на объекте клиента Windows Communication Foundation (WCF) или на объекте фабрики каналов клиента перед открытием клиента.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как программным образом вставить поведение, обратившись к свойству <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> объекта <xref:System.ServiceModel.Description.ServiceEndpoint>, возвращаемого свойством <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> до создания объекта канала.  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a>См. также
- [\<варианты поведения >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
