---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 47a7d862cf85254f88373d582169ff421be2b5b8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115834"
---
# <a name="comcontracts"></a><span data-ttu-id="89784-101">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="89784-101">\<comContracts></span></span>
<span data-ttu-id="89784-102">Раздел конфигурации `comContracts` содержит элементы, которые позволяют задавать различные свойства контракта службы интеграции COM+.</span><span class="sxs-lookup"><span data-stu-id="89784-102">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="89784-103">Задание пространства имен и контракта</span><span class="sxs-lookup"><span data-stu-id="89784-103">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="89784-104">Контракты службы интеграции COM +, в настоящее время ограничены `http://tempuri.org` пространства имен, а имя контракта является производным от поддерживающего COM-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="89784-104">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="89784-105">Однако можно указать альтернативы, используя раздел `comContracts` в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="89784-105">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="89784-106">Например, для указания пространства имен, имени контракта службы и параметра для принудительного использования сеансовых привязок можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="89784-106">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="89784-107">После инициализации службы указанные пространства имен и имена контрактов применяются к созданным описаниям служб.</span><span class="sxs-lookup"><span data-stu-id="89784-107">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="89784-108">Если раздел пуст, при инициализации службы применяется пространство имен по умолчанию и имя контракта, взятое из идентификатора поддерживающего COM-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="89784-108">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="89784-109">Кроме того, можно использовать [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элемент для задания методов COM +, которые предоставляются при предоставлении интерфейса компонента COM + предоставляется как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="89784-109">In addition, you can use the [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="89784-110">Можно также использовать [ \<persistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) для задания неизменных типов, используемых в интеграции.</span><span class="sxs-lookup"><span data-stu-id="89784-110">You can also use the [\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="89784-111">Наконец, вы можете использовать [ \<userDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) элемент для включения пользовательских типов (UDT), должны быть включены в контракте службы.</span><span class="sxs-lookup"><span data-stu-id="89784-111">Finally, you can use the [\<userDefinedType>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89784-112">См. также</span><span class="sxs-lookup"><span data-stu-id="89784-112">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="89784-113">\<exposedMethod ></span><span class="sxs-lookup"><span data-stu-id="89784-113">\<exposedMethod></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)
- [<span data-ttu-id="89784-114">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="89784-114">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)
- [<span data-ttu-id="89784-115">\<userDefinedType ></span><span class="sxs-lookup"><span data-stu-id="89784-115">\<userDefinedType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)
- [<span data-ttu-id="89784-116">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="89784-116">\<comContract></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)
- [<span data-ttu-id="89784-117">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="89784-117">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="89784-118">Практическое руководство. Настройка параметров службы COM +</span><span class="sxs-lookup"><span data-stu-id="89784-118">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
