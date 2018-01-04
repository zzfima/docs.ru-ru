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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee79900b52ae0fa58e8fb9a5cbbf50f5a882c295
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-client-behaviors"></a><span data-ttu-id="ef24e-102">Настройка поведений клиентов</span><span class="sxs-lookup"><span data-stu-id="ef24e-102">Configuring Client Behaviors</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="ef24e-103"> настраивает поведение двумя способами: путем ссылки на конфигурации поведения (которые определяются в разделе `<behavior>` файла конфигурации приложения) или программным образом в вызывающем приложении.</span><span class="sxs-lookup"><span data-stu-id="ef24e-103"> configures behaviors in two ways: either by referring to behavior configurations -- which are defined in the `<behavior>` section of a client application configuration file – or programmatically in the calling application.</span></span> <span data-ttu-id="ef24e-104">В этом разделе описываются оба подхода.</span><span class="sxs-lookup"><span data-stu-id="ef24e-104">This topic describes both approaches.</span></span>  
  
 <span data-ttu-id="ef24e-105">При использовании файла конфигурации конфигурация поведения представляет собой именованную коллекцию параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ef24e-105">When using a configuration file, behavior configuration is a named collection of configuration settings.</span></span> <span data-ttu-id="ef24e-106">Имя каждой из конфигураций поведения должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="ef24e-106">The name of each behavior configuration must be unique.</span></span> <span data-ttu-id="ef24e-107">Эта строка используется в атрибуте `behaviorConfiguration` конфигурации конечной точки, чтобы связать конечную точку с поведением.</span><span class="sxs-lookup"><span data-stu-id="ef24e-107">This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef24e-108">Пример</span><span class="sxs-lookup"><span data-stu-id="ef24e-108">Example</span></span>  
 <span data-ttu-id="ef24e-109">В следующем фрагменте кода конфигурации определяется поведение с именем `myBehavior`.</span><span class="sxs-lookup"><span data-stu-id="ef24e-109">The following configuration code defines a behavior called `myBehavior`.</span></span> <span data-ttu-id="ef24e-110">Конечная точка клиента ссылается на это поведение в атрибуте `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="ef24e-110">The client endpoint references this behavior in the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="using-behaviors-programmatically"></a><span data-ttu-id="ef24e-111">Управление поведениями программным образом</span><span class="sxs-lookup"><span data-stu-id="ef24e-111">Using Behaviors Programmatically</span></span>  
 <span data-ttu-id="ef24e-112">Можно также настраивать или вставлять поведения программным образом путем поиска соответствующего свойства `Behaviors` в клиентском объекте [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] или в объекте клиентской фабрики каналов до того, как открыть клиент.</span><span class="sxs-lookup"><span data-stu-id="ef24e-112">You can also configure or insert behaviors programmatically by locating the appropriate `Behaviors` property on the [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] client object or on the client channel factory object prior to opening the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef24e-113">Пример</span><span class="sxs-lookup"><span data-stu-id="ef24e-113">Example</span></span>  
 <span data-ttu-id="ef24e-114">В следующем примере кода показано, как программным образом вставить поведение, обратившись к свойству <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> объекта <xref:System.ServiceModel.Description.ServiceEndpoint>, возвращаемого свойством <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> до создания объекта канала.</span><span class="sxs-lookup"><span data-stu-id="ef24e-114">The following code example shows how to programmatically insert a behavior by accessing the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property on the <xref:System.ServiceModel.Description.ServiceEndpoint> returned from the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property prior to the creation of the channel object.</span></span>  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="ef24e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ef24e-115">See Also</span></span>  
 [<span data-ttu-id="ef24e-116">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="ef24e-116">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
