---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: d061d48374a8745dc61e1ca156e4fcbbccee5ef7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919473"
---
# <a name="comcontracts"></a><span data-ttu-id="dccac-101">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="dccac-101">\<comContracts></span></span>
<span data-ttu-id="dccac-102">Раздел конфигурации `comContracts` содержит элементы, которые позволяют задавать различные свойства контракта службы интеграции COM+.</span><span class="sxs-lookup"><span data-stu-id="dccac-102">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="dccac-103">Задание пространства имен и контракта</span><span class="sxs-lookup"><span data-stu-id="dccac-103">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="dccac-104">Контракты службы интеграции COM+ в настоящее время ограничены `http://tempuri.org` пространством имен, а имя контракта является производным от поддерживающего com-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="dccac-104">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="dccac-105">Однако можно указать альтернативы, используя раздел `comContracts` в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dccac-105">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="dccac-106">Например, для указания пространства имен, имени контракта службы и параметра для принудительного использования сеансовых привязок можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="dccac-106">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="dccac-107">После инициализации службы указанные пространства имен и имена контрактов применяются к созданным описаниям служб.</span><span class="sxs-lookup"><span data-stu-id="dccac-107">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="dccac-108">Если раздел пуст, при инициализации службы применяется пространство имен по умолчанию и имя контракта, взятое из идентификатора поддерживающего COM-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="dccac-108">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="dccac-109">Кроме того, можно использовать [ \<элемент > exposedMethod](exposedmethod.md) , чтобы указать методы COM+, которые предоставляются, когда интерфейс в компоненте com+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="dccac-109">In addition, you can use the [\<exposedMethod>](exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="dccac-110">Можно также использовать [ \<> персистаблетипес](persistabletypes.md) , чтобы указать сохраняемые типы, используемые при интеграции.</span><span class="sxs-lookup"><span data-stu-id="dccac-110">You can also use the [\<persistableTypes>](persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="dccac-111">Наконец, можно использовать [ \<элемент userDefinedType >](userdefinedtype.md) для включения определяемых пользователем типов (UDT), которые должны быть включены в контракт службы.</span><span class="sxs-lookup"><span data-stu-id="dccac-111">Finally, you can use the [\<userDefinedType>](userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dccac-112">См. также</span><span class="sxs-lookup"><span data-stu-id="dccac-112">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="dccac-113">\<exposedMethod ></span><span class="sxs-lookup"><span data-stu-id="dccac-113">\<exposedMethod></span></span>](exposedmethod.md)
- [<span data-ttu-id="dccac-114">\<Персистаблетипес ></span><span class="sxs-lookup"><span data-stu-id="dccac-114">\<persistableTypes></span></span>](persistabletypes.md)
- [<span data-ttu-id="dccac-115">\<userDefinedType ></span><span class="sxs-lookup"><span data-stu-id="dccac-115">\<userDefinedType></span></span>](userdefinedtype.md)
- [<span data-ttu-id="dccac-116">\<Комконтракт ></span><span class="sxs-lookup"><span data-stu-id="dccac-116">\<comContract></span></span>](comcontract.md)
- [<span data-ttu-id="dccac-117">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="dccac-117">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="dccac-118">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="dccac-118">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
