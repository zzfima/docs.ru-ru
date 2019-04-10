---
title: Настройка значений времени ожидания для привязки
ms.date: 03/30/2017
ms.assetid: b5c825a2-b48f-444a-8659-61751ff11d34
ms.openlocfilehash: f323dfff338f8a3ba24caab6df3b3916d3ae0d13
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339766"
---
# <a name="configuring-timeout-values-on-a-binding"></a><span data-ttu-id="6f4e0-102">Настройка значений времени ожидания для привязки</span><span class="sxs-lookup"><span data-stu-id="6f4e0-102">Configuring Timeout Values on a Binding</span></span>
<span data-ttu-id="6f4e0-103">Существует ряд настроек параметров времени ожидания, доступных в привязках WCF.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-103">There are a number of timeout settings available in WCF bindings.</span></span> <span data-ttu-id="6f4e0-104">Правильная установка этих параметров времени ожидания может не только повысить производительность службы, но и внести вклад в удобство использования и безопасность службы.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-104">Setting these timeout settings correctly can improve not only your service’s performance but also play a role in the usability and security of your service.</span></span> <span data-ttu-id="6f4e0-105">Доступны следующие значения времени ожидания для привязок WCF.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-105">The following timeouts are available on WCF bindings:</span></span>  
  
1. <span data-ttu-id="6f4e0-106">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="6f4e0-106">OpenTimeout</span></span>  
  
2. <span data-ttu-id="6f4e0-107">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="6f4e0-107">CloseTimeout</span></span>  
  
3. <span data-ttu-id="6f4e0-108">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="6f4e0-108">SendTimeout</span></span>  
  
4. <span data-ttu-id="6f4e0-109">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="6f4e0-109">ReceiveTimeout</span></span>  
  
## <a name="wcf-binding-timeouts"></a><span data-ttu-id="6f4e0-110">Время ожидания привязок WCF</span><span class="sxs-lookup"><span data-stu-id="6f4e0-110">WCF Binding Timeouts</span></span>  
 <span data-ttu-id="6f4e0-111">Каждый из параметров, описанный в этом разделе, применяется к самой привязке, в коде или в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-111">Each of the settings discussed in this topic are made on the binding itself, either in code or configuration.</span></span> <span data-ttu-id="6f4e0-112">В следующем примере кода показано, как программно задать время ожидания для привязки WCF в контексте резидентной службы.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-112">The following code shows how to programmatically set timeouts on a WCF binding in the context of a self-hosted service.</span></span>  
  
```csharp  
public static void Main()
{
    Uri baseAddress = new Uri("http://localhost/MyServer/MyService");
    
    try
    {
        ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService));
        
        WSHttpBinding binding = new WSHttpBinding();
        binding.OpenTimeout = new TimeSpan(0, 10, 0);
        binding.CloseTimeout = new TimeSpan(0, 10, 0);
        binding.SendTimeout = new TimeSpan(0, 10, 0);
        binding.ReceiveTimeout = new TimeSpan(0, 10, 0);
        
        serviceHost.AddServiceEndpoint("ICalculator", binding, baseAddress);
        serviceHost.Open();
        
        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();
    }
    catch (CommunicationException ex)
    {
        // Handle exception ...
    }
}
```  
  
 <span data-ttu-id="6f4e0-113">В следующем примере показано, как настроить время ожидания привязки в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-113">The following example shows how to configure timeouts on a binding in a configuration file.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding openTimeout="00:10:00" 
                 closeTimeout="00:10:00" 
                 sendTimeout="00:10:00" 
                 receiveTimeout="00:10:00">
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
 <span data-ttu-id="6f4e0-114">Дополнительные сведения об этих параметрах можно найти в документации по классу <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-114">More information about these settings can be found in the documentation for the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
### <a name="client-side-timeouts"></a><span data-ttu-id="6f4e0-115">Время ожидания на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="6f4e0-115">Client-side Timeouts</span></span>  
 <span data-ttu-id="6f4e0-116">На стороне клиента:</span><span class="sxs-lookup"><span data-stu-id="6f4e0-116">On the client side:</span></span>  
  
1. <span data-ttu-id="6f4e0-117">Значение SendTimeout используется для инициализации значения OperationTimeout, которое управляет всем процессом отправки сообщения, включая получение ответного сообщения для операции службы типа «запрос-ответ».</span><span class="sxs-lookup"><span data-stu-id="6f4e0-117">SendTimeout – used to initialize the OperationTimeout, which governs the whole process of sending a message, including receiving a reply message for a request/reply service operation.</span></span> <span data-ttu-id="6f4e0-118">Это время ожидания применяется также при отправке ответного сообщения из метода обратного вызова контракта.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-118">This timeout also applies when sending reply messages from a callback contract method.</span></span>  
  
2. <span data-ttu-id="6f4e0-119">Значение OpenTimeout используется при открытии каналов, если не задан явно заданным временем ожидания.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-119">OpenTimeout – used when opening channels when no explicit timeout value is specified.</span></span>  
  
3. <span data-ttu-id="6f4e0-120">Значение CloseTimeout используется при закрытии каналов, если не задан явно заданным временем ожидания.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-120">CloseTimeout – used when closing channels when no explicit timeout value is specified.</span></span>  
  
4. <span data-ttu-id="6f4e0-121">Значение ReceiveTimeout не используется.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-121">ReceiveTimeout – is not used.</span></span>  
  
### <a name="service-side-timeouts"></a><span data-ttu-id="6f4e0-122">Время ожидания на стороне службы</span><span class="sxs-lookup"><span data-stu-id="6f4e0-122">Service-side Timeouts</span></span>  
 <span data-ttu-id="6f4e0-123">На стороне службы:</span><span class="sxs-lookup"><span data-stu-id="6f4e0-123">On the service side:</span></span>  
  
1. <span data-ttu-id="6f4e0-124">SendTimeout, OpenTimeout, CloseTimeout одинаковы как на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-124">SendTimeout, OpenTimeout, CloseTimeout are the same as on the client.</span></span>  
  
2. <span data-ttu-id="6f4e0-125">Значение ReceiveTimeout используется на уровне платформы службы для инициализации времени ожидания бездействующего сеанса. Это время ожидания определяет, как долго сеанс может находиться в бездействии до истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-125">ReceiveTimeout – used by the Service Framework Layer to initialize the session-idle timeout which controls how long a session can be idle before timing out.</span></span>
