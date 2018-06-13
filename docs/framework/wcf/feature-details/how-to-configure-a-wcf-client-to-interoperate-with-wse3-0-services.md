---
title: Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: e30403f9c97f31e93c22a9658ffb74d4d02a49ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490647"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="c3c18-102">Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="c3c18-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
<span data-ttu-id="c3c18-103">Клиенты Windows Communication Foundation (WCF) находятся транспортного уровня совместимости с веб-служб версии 3.0 для служб Microsoft .NET (WSE), когда WCF клиенты настроены для использования версии спецификации WS-Addressing августа 2004 г.</span><span class="sxs-lookup"><span data-stu-id="c3c18-103">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="c3c18-104">Настройка клиента WCF для взаимодействия с веб-службой WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="c3c18-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1.  <span data-ttu-id="c3c18-105">Запустите [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания клиента WCF для службы WSE 3.0 Web.</span><span class="sxs-lookup"><span data-stu-id="c3c18-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="c3c18-106">Для веб-службы WSE создается класс клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="c3c18-106">For a WSE Web service, a WCF client class is created.</span></span>  
  
     <span data-ttu-id="c3c18-107">Дополнительные сведения о создании WCF-клиента см. в разделе [как: создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="c3c18-107">For details about creating a WCF client, see the [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="c3c18-108">Создайте класс, представляющий привязку, которая может обмениваться данными с веб-службами WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="c3c18-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="c3c18-109">Следующий класс является частью [взаимодействия с WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) образца.</span><span class="sxs-lookup"><span data-stu-id="c3c18-109">The following class is part of the [Interoperating with WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) sample.</span></span>  
  
    1.  <span data-ttu-id="c3c18-110">Создайте класс, производный от класса <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="c3c18-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="c3c18-111">В следующем примере кода создается класс с именем `WseHttpBinding`, наследуемый от класса <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="c3c18-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  <span data-ttu-id="c3c18-112">Добавьте в класс свойства, задающие готовое к использованию утверждение WSE, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение подписей, и параметры защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="c3c18-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="c3c18-113">В следующем примере кода определяется `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` свойства, задающие готовое к использованию утверждение WSE, требуются ли производные ключи, используются ли безопасные сеансы, требуются ли подтверждение подписей и параметры защиты сообщений соответственно.</span><span class="sxs-lookup"><span data-stu-id="c3c18-113">The following code example defines `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` properties that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  <span data-ttu-id="c3c18-114">Переопределите метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> для задания свойств привязки.</span><span class="sxs-lookup"><span data-stu-id="c3c18-114">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="c3c18-115">В следующем примере кода транспорт, кодирование сообщений и параметры защиты сообщений задаются получением значений свойств `SecurityAssertion` и `MessageProtectionOrder`.</span><span class="sxs-lookup"><span data-stu-id="c3c18-115">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  <span data-ttu-id="c3c18-116">В коде клиентского приложения добавьте код для задания свойств привязки.</span><span class="sxs-lookup"><span data-stu-id="c3c18-116">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="c3c18-117">В следующем примере кода указывает, что клиент WCF необходимо использовать защиту сообщений и проверки подлинности в соответствии с определением WSE 3.0 `AnonymousForCertificate` использованию утверждением безопасности.</span><span class="sxs-lookup"><span data-stu-id="c3c18-117">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="c3c18-118">Кроме того, требуются безопасные сеансы и производные ключи.</span><span class="sxs-lookup"><span data-stu-id="c3c18-118">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="c3c18-119">Пример</span><span class="sxs-lookup"><span data-stu-id="c3c18-119">Example</span></span>  
 <span data-ttu-id="c3c18-120">В следующем примере кода определяется пользовательская привязка, предоставляющая свойства, соответствующие свойствам готового к использованию утверждения безопасности WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="c3c18-120">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="c3c18-121">Пользовательские привязки, который называется `WseHttpBinding`, используется для задания свойств привязки для клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="c3c18-121">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client.</span></span>  
  
  
[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="c3c18-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c3c18-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 [<span data-ttu-id="c3c18-123">Взаимодействие с WSE</span><span class="sxs-lookup"><span data-stu-id="c3c18-123">Interoperating with WSE</span></span>](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)
