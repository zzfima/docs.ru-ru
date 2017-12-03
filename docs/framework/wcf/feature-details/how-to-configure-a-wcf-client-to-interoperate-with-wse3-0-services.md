---
title: "Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0"
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
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 901b75e1683a830d32428685a33afb63ace29a8f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="31720-102">Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="31720-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
<span data-ttu-id="31720-103">Клиенты [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] на уровне линий связи совместимы со службами расширений веб-служб версии 3.0 для Microsoft .NET (WSE), если клиенты [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] настроены на использование спецификации WS-Addressing версии августа 2004 г.</span><span class="sxs-lookup"><span data-stu-id="31720-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="31720-104">Настройка клиента WCF для взаимодействия с веб-службой WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="31720-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1.  <span data-ttu-id="31720-105">Запустите [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиента для службы WSE 3.0 Web.</span><span class="sxs-lookup"><span data-stu-id="31720-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="31720-106">Для веб-службы WSE создается класс клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31720-106">For a WSE Web service, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class is created.</span></span>  
  
     <span data-ttu-id="31720-107">Дополнительные сведения о создании [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиента, в разделе [как: создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="31720-107">For details about creating a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, see the [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="31720-108">Создайте класс, представляющий привязку, которая может обмениваться данными с веб-службами WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="31720-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="31720-109">Следующий класс является частью [взаимодействия с WSE](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41) образца.</span><span class="sxs-lookup"><span data-stu-id="31720-109">The following class is part of the [Interoperating with WSE](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41) sample.</span></span>  
  
    1.  <span data-ttu-id="31720-110">Создайте класс, производный от класса <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="31720-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="31720-111">В следующем примере кода создается класс с именем `WseHttpBinding`, наследуемый от класса <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="31720-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  <span data-ttu-id="31720-112">Добавьте в класс свойства, задающие готовое к использованию утверждение WSE, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение подписей, и параметры защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="31720-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="31720-113">В следующем примере кода определяется `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` свойства, задающие готовое к использованию утверждение WSE, требуются ли производные ключи, используются ли безопасные сеансы, требуются ли подтверждение подписей и параметры защиты сообщений соответственно.</span><span class="sxs-lookup"><span data-stu-id="31720-113">The following code example defines `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` properties that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  <span data-ttu-id="31720-114">Переопределите метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> для задания свойств привязки.</span><span class="sxs-lookup"><span data-stu-id="31720-114">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="31720-115">В следующем примере кода транспорт, кодирование сообщений и параметры защиты сообщений задаются получением значений свойств `SecurityAssertion` и `MessageProtectionOrder`.</span><span class="sxs-lookup"><span data-stu-id="31720-115">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  <span data-ttu-id="31720-116">В коде клиентского приложения добавьте код для задания свойств привязки.</span><span class="sxs-lookup"><span data-stu-id="31720-116">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="31720-117">В следующем примере кода указывается, что клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] должен использовать защиту сообщений и проверку подлинности в соответствии с готовым к использованию утверждением безопасности WSE 3.0 `AnonymousForCertificate`.</span><span class="sxs-lookup"><span data-stu-id="31720-117">The following code example specifies that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="31720-118">Кроме того, требуются безопасные сеансы и производные ключи.</span><span class="sxs-lookup"><span data-stu-id="31720-118">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="31720-119">Пример</span><span class="sxs-lookup"><span data-stu-id="31720-119">Example</span></span>  
 <span data-ttu-id="31720-120">В следующем примере кода определяется пользовательская привязка, предоставляющая свойства, соответствующие свойствам готового к использованию утверждения безопасности WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="31720-120">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="31720-121">Затем пользовательская привязка с именем `WseHttpBinding` используется для задания свойств привязки для клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31720-121">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client.</span></span>  
  
  
[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="31720-122">См. также</span><span class="sxs-lookup"><span data-stu-id="31720-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 [<span data-ttu-id="31720-123">Взаимодействие с WSE</span><span class="sxs-lookup"><span data-stu-id="31720-123">Interoperating with WSE</span></span>](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41)
