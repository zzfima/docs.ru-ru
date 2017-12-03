---
title: "Практическое руководство. Настройка параметров службы COM+"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: COM+ [WCF], configuring service settings
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa497567c5cf380d7764499991ad9e7e95a5cbe0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-com-service-settings"></a><span data-ttu-id="e4902-102">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="e4902-102">How to: Configure COM+ Service Settings</span></span>
<span data-ttu-id="e4902-103">Если интерфейс приложения добавляется или удаляется с использованием средства конфигурации служб COM+, конфигурация веб-службы обновляется в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e4902-103">When an application interface is added or removed by using the COM+ Service Configuration tool, the Web service configuration is updated within the application's configuration file.</span></span> <span data-ttu-id="e4902-104">В режиме служб COM + файл Application.config помещается в корневую папку приложения (приложения %PROGRAMFILES%\ComPlus\\по умолчанию — {appid}).</span><span class="sxs-lookup"><span data-stu-id="e4902-104">In the COM+ hosted mode, the Application.config file is placed in the Application Root Directory (%PROGRAMFILES%\ComPlus Applications\\{appid} is the default).</span></span> <span data-ttu-id="e4902-105">В обоих режимах размещения на веб-сервере файл Web.config помещается в заданный виртуальный корневой каталог.</span><span class="sxs-lookup"><span data-stu-id="e4902-105">In either of the Web-hosted modes, the Web.config file is placed in the specified vroot directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4902-106">Для защиты от подделки сообщений, обмен которыми выполняется между клиентом и сервером, необходимо использовать подписывание сообщения.</span><span class="sxs-lookup"><span data-stu-id="e4902-106">Message signing should be used to protect against tampering of messages between a client and a server.</span></span> <span data-ttu-id="e4902-107">Кроме того, для защиты от раскрытия информации, содержащейся в сообщениях, обмен которыми выполняется между клиентом и сервером, следует использовать шифрование на уровне сообщения или транспорта.</span><span class="sxs-lookup"><span data-stu-id="e4902-107">Also, message or transport layer encryption should be used to protect against information disclosure from messages between a client and a server.</span></span> <span data-ttu-id="e4902-108">Как и в случае служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] необходимо использовать функцию регулирования, чтобы ограничить количество одновременных вызовов, подключений, экземпляров и отложенных операций.</span><span class="sxs-lookup"><span data-stu-id="e4902-108">As with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services, you should use throttling to limit the number of concurrent calls, connections, instances, and pending operations.</span></span> <span data-ttu-id="e4902-109">Это помогает предотвратить чрезмерное потребление ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e4902-109">This helps prevent over-consumption of resources.</span></span> <span data-ttu-id="e4902-110">Поведение регулирования задается параметрами файла конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="e4902-110">Throttling behavior is specified through service configuration file settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4902-111">Пример</span><span class="sxs-lookup"><span data-stu-id="e4902-111">Example</span></span>  
 <span data-ttu-id="e4902-112">Рассмотрим компонент, реализующий следующий интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e4902-112">Consider a component that implements the following interface:</span></span>  
  
```  
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
```  
  
 <span data-ttu-id="e4902-113">Если компонент предоставляется как веб-служба, соответствующий предоставляемый контракт службы, которому должны соответствовать клиенты, выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e4902-113">If the component is exposed as a Web service, the corresponding service contract that is exposed, and that clients would need to conform to, is as follows:</span></span>  
  
```  
[ServiceContract(Session = true,  
Namespace = "http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7",  
Name = "IFinances")]  
public interface IFinancesContract : IDisposable  
{  
    [OperationContract]  
    string Debit(string accountNo, double amount);  
    [OperationContract]  
    string Credit(string accountNo, double amount);  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="e4902-114">Идентификатор интерфейса формирует часть исходного пространства имен для контракта.</span><span class="sxs-lookup"><span data-stu-id="e4902-114">IID forms part of the initial namespace for the contract.</span></span>  
  
 <span data-ttu-id="e4902-115">Клиентские приложения, использующие эту службу, должны соответствовать этому контракту, а также использовать привязку, совместимую с привязкой, заданной в конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e4902-115">Client applications that use this service would need to conform to this contract, along with using a binding that is compatible with the one specified in the application configuration.</span></span>  
  
 <span data-ttu-id="e4902-116">В следующем примере кода показан файл конфигурации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e4902-116">The following code example shows a default configuration file.</span></span> <span data-ttu-id="e4902-117">Являясь веб-службой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], он соответствует стандартной схеме конфигурации модели службы, и его можно изменить так же, как другие файлы конфигурации служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4902-117">Being a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web service, this conforms to the standard service model configuration schema and can be edited in the same way as other [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services configuration files.</span></span>  
  
 <span data-ttu-id="e4902-118">Типичные изменения включают следующее.</span><span class="sxs-lookup"><span data-stu-id="e4902-118">Typical modifications would include:</span></span>  
  
-   <span data-ttu-id="e4902-119">Изменение адреса конечной точки с формы ApplicationName/ComponentName/InterfaceName по умолчанию на более удобную форму.</span><span class="sxs-lookup"><span data-stu-id="e4902-119">Changing the endpoint address from the default ApplicationName/ComponentName/InterfaceName form to a more usable form.</span></span>  
  
-   <span data-ttu-id="e4902-120">Изменение пространства имен службы с формы "http://tempuri.org/InterfaceID" по умолчанию на более подходящую форму.</span><span class="sxs-lookup"><span data-stu-id="e4902-120">Modifying the namespace of the service from the default "http://tempuri.org/InterfaceID" form to a more relevant form.</span></span>  
  
-   <span data-ttu-id="e4902-121">Изменение настройки конечной точки, чтобы она использовала другую привязку транспорта.</span><span class="sxs-lookup"><span data-stu-id="e4902-121">Changing the endpoint to use a different transport binding.</span></span>  
  
     <span data-ttu-id="e4902-122">В случае размещения в COM+ по умолчанию используется транспорт именованных каналов, но вместо него можно использовать транспорт вне компьютера, такой как TCP.</span><span class="sxs-lookup"><span data-stu-id="e4902-122">In the COM+-hosted case, the named pipes transport is used by default, but an off-machine transport like TCP can be used instead.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="comNonTransactionalBinding" />  
                <binding name="comTransactionalBinding" transactionFlow="true" />  
            </netNamedPipeBinding>  
        </bindings>  
        <comContracts>  
            <comContract contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"  
                name="IFinances" namespace="http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7"  
                requiresSession="true">  
                <exposedMethods>  
                    <add exposedMethod="Debit" />  
                    <add exposedMethod="Credit" />  
                </exposedMethods>  
            </comContract>  
        </comContracts>  
        <services>  
            <service name="{DCDB24CC-0B19-4534-95CD-FBBFF4D67DD9},{C942B840-AD54-4A44-B5F7-928130980AB9}">  
                <endpoint address="IFinances" binding="netNamedPipeBinding" bindingConfiguration="comNonTransactionalBinding"  
                    contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" />  
                <host>  
                    <baseAddresses>  
                        <add baseAddress="net.pipe://localhost/ServiceModelDocSampleApp/ServiceModelDocSample.esFinance" />  
                    </baseAddresses>  
                </host>  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4902-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e4902-123">See Also</span></span>  
 [<span data-ttu-id="e4902-124">Интеграция с приложениями COM +</span><span class="sxs-lookup"><span data-stu-id="e4902-124">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
