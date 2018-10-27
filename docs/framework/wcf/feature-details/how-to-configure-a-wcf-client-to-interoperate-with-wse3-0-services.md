---
title: Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: 5cbe982049d1df6e2c714ca0b63de0db7577452e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187313"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="66857-102">Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="66857-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
<span data-ttu-id="66857-103">Клиенты Windows Communication Foundation (WCF) являются уровне линий связи совместимы с Web Services Enhancements 3.0 для служб Microsoft .NET (WSE), если WCF клиенты настроены для использования версии спецификации WS-Addressing от августа 2004 г.</span><span class="sxs-lookup"><span data-stu-id="66857-103">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="66857-104">Настройка клиента WCF для взаимодействия с веб-службой WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="66857-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1.  <span data-ttu-id="66857-105">Запустите [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) создание клиента WCF для WSE 3.0 веб-службы.</span><span class="sxs-lookup"><span data-stu-id="66857-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="66857-106">Для веб-службы WSE создается класс клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="66857-106">For a WSE Web service, a WCF client class is created.</span></span>  
  
     <span data-ttu-id="66857-107">Дополнительные сведения о создании клиента WCF, см. в разделе [как: создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="66857-107">For details about creating a WCF client, see the [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="66857-108">Создайте класс, представляющий привязку, которая может обмениваться данными с веб-службами WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="66857-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="66857-109">Следующий класс является частью [взаимодействие с WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) образца.</span><span class="sxs-lookup"><span data-stu-id="66857-109">The following class is part of the [Interoperating with WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) sample.</span></span>  
  
    1.  <span data-ttu-id="66857-110">Создайте класс, производный от класса <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="66857-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="66857-111">В следующем примере кода создается класс с именем `WseHttpBinding`, наследуемый от класса <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="66857-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  <span data-ttu-id="66857-112">Добавьте в класс свойства, задающие готовое к использованию утверждение WSE, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение подписей, и параметры защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="66857-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="66857-113">В следующем примере кода определяется `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` свойства, задающие готовое к использованию утверждение WSE, требуются ли производные ключи, используются ли безопасные сеансы, требуются ли подтверждение подписей и параметры защиты сообщений, соответственно.</span><span class="sxs-lookup"><span data-stu-id="66857-113">The following code example defines `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` properties that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  <span data-ttu-id="66857-114">Переопределите метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> для задания свойств привязки.</span><span class="sxs-lookup"><span data-stu-id="66857-114">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="66857-115">В следующем примере кода транспорт, кодирование сообщений и параметры защиты сообщений задаются получением значений свойств `SecurityAssertion` и `MessageProtectionOrder`.</span><span class="sxs-lookup"><span data-stu-id="66857-115">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  <span data-ttu-id="66857-116">В коде клиентского приложения добавьте код для задания свойств привязки.</span><span class="sxs-lookup"><span data-stu-id="66857-116">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="66857-117">В следующем примере кода указывает, что клиент WCF должна использовать защиту сообщений и проверки подлинности, как определено в WSE 3.0 `AnonymousForCertificate` утверждение готовое к использованию безопасности.</span><span class="sxs-lookup"><span data-stu-id="66857-117">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="66857-118">Кроме того, требуются безопасные сеансы и производные ключи.</span><span class="sxs-lookup"><span data-stu-id="66857-118">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="66857-119">Пример</span><span class="sxs-lookup"><span data-stu-id="66857-119">Example</span></span>  
 <span data-ttu-id="66857-120">В следующем примере кода определяется пользовательская привязка, предоставляющая свойства, соответствующие свойствам готового к использованию утверждения безопасности WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="66857-120">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="66857-121">Пользовательская привязка, которая называется `WseHttpBinding`, затем используется для задания свойств привязки для клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="66857-121">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client.</span></span>  
  
  
[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="66857-122">См. также</span><span class="sxs-lookup"><span data-stu-id="66857-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 [<span data-ttu-id="66857-123">Взаимодействие с WSE</span><span class="sxs-lookup"><span data-stu-id="66857-123">Interoperating with WSE</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)