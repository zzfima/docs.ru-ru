---
title: Безопасность сообщений с использованием механизмов Windows
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: d2221d1c-c9cb-48d1-b044-a3b4445c7f05
ms.openlocfilehash: eed16f6231717119b30003451cef5eb54016678c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772606"
---
# <a name="message-security-windows"></a><span data-ttu-id="ea5cf-102">Безопасность сообщений с использованием механизмов Windows</span><span class="sxs-lookup"><span data-stu-id="ea5cf-102">Message Security Windows</span></span>
<span data-ttu-id="ea5cf-103">В этом образце показывается, как настраивать привязку <xref:System.ServiceModel.WSHttpBinding> для использования безопасности на уровне сообщений с проверкой подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="ea5cf-103">This sample demonstrates how to configure a <xref:System.ServiceModel.WSHttpBinding> binding to use message-level security with Windows authentication.</span></span> <span data-ttu-id="ea5cf-104">Этот образец основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ea5cf-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="ea5cf-105">В этом образце служба размещается в службах IIS, а клиентом является консольное приложение (EXE).</span><span class="sxs-lookup"><span data-stu-id="ea5cf-105">In this sample, the service is hosted in Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea5cf-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="ea5cf-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ea5cf-107">Безопасность по умолчанию для [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) является безопасность сообщений с использованием проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="ea5cf-107">The default security for the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) is message security using Windows authentication.</span></span> <span data-ttu-id="ea5cf-108">Файлы конфигурации в этом примере явно задать `mode` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) для `Message` и `clientCredentialType` атрибут `Windows`.</span><span class="sxs-lookup"><span data-stu-id="ea5cf-108">The configuration files in this sample explicitly set the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) to `Message` and the `clientCredentialType` attribute to `Windows`.</span></span> <span data-ttu-id="ea5cf-109">Эти значения являются значениями по умолчанию для этой привязки, но они были явно заданы, как показано в следующем образце конфигурации с целью демонстрации их использования.</span><span class="sxs-lookup"><span data-stu-id="ea5cf-109">These values are the default values for this binding, but they have been explicitly configured, as shown in the following sample configuration to demonstrate their use.</span></span>  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding>  
            <security mode="Message">  
                <message clientCredentialType="Windows"/>  
            </security>  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="ea5cf-110">Конфигурация конечной точки клиента состоит из абсолютного адреса конечной точки службы, привязки и контракта.</span><span class="sxs-lookup"><span data-stu-id="ea5cf-110">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="ea5cf-111">Привязка клиента настраивается с помощью соответствующих `securityMode` и `authenticationMode`.</span><span class="sxs-lookup"><span data-stu-id="ea5cf-111">The client binding is configured with the appropriate `securityMode` and `authenticationMode`.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address=  
            "http://localhost/servicemodelsamples/service.svc"   
            binding="wsHttpBinding"   
            bindingConfiguration="Binding1"   
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- The default security for the WSHttpBinding is -->  
      <!-- Message security using Windows authentication. -->  
      <!-- This configuration explicitly defines the security mode -->  
      <!-- as Message and the clientCredentialType as Windows -->  
      <!-- for demonstration purposes. -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="Windows"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="ea5cf-112">Исходный код службы был изменен, чтобы показать, как можно использовать <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> для доступа к идентификатору вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="ea5cf-112">The service source code has been modified to demonstrate how the <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> can be used to access the identity of the caller.</span></span>  

```csharp
public string GetCallerIdentity()  
{  
    // The Windows identity of the caller can be accessed on the ServiceSecurityContext.WindowsIdentity.  
    return OperationContext.Current.ServiceSecurityContext.WindowsIdentity.Name;  
}  
```

 <span data-ttu-id="ea5cf-113">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="ea5cf-113">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="ea5cf-114">Первый вызываемый метод - `GetCallerIdentity` - возвращает имя идентификатора вызывающего объекта для клиента.</span><span class="sxs-lookup"><span data-stu-id="ea5cf-114">The first method called - `GetCallerIdentity` - returns the name of the caller identity back to the client.</span></span> <span data-ttu-id="ea5cf-115">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="ea5cf-115">Press ENTER in the console window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ea5cf-116">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="ea5cf-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ea5cf-117">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ea5cf-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ea5cf-118">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ea5cf-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ea5cf-119">Чтобы запустить образец в конфигурации с одной или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ea5cf-119">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
