---
title: '&lt;comContract&gt;'
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 8e0e18c934589e89ff5e10b14ba02f8daee11c66
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146879"
---
# <a name="ltcomcontractgt"></a><span data-ttu-id="ec295-102">&lt;comContract&gt;</span><span class="sxs-lookup"><span data-stu-id="ec295-102">&lt;comContract&gt;</span></span>
<span data-ttu-id="ec295-103">Указывает контракт службы интеграции COM+.</span><span class="sxs-lookup"><span data-stu-id="ec295-103">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="ec295-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ec295-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ec295-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="ec295-105">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec295-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec295-106">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract contract="String"
               namespace="String"
               name="String"
               requireSession="Boolean">
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec295-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ec295-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ec295-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ec295-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec295-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ec295-109">Attributes</span></span>  
  
|<span data-ttu-id="ec295-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ec295-110">Attribute</span></span>|<span data-ttu-id="ec295-111">Описание</span><span class="sxs-lookup"><span data-stu-id="ec295-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec295-112">контракт</span><span class="sxs-lookup"><span data-stu-id="ec295-112">contract</span></span>|<span data-ttu-id="ec295-113">Строка, содержащая тип контракта.</span><span class="sxs-lookup"><span data-stu-id="ec295-113">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="ec295-114">имя</span><span class="sxs-lookup"><span data-stu-id="ec295-114">name</span></span>|<span data-ttu-id="ec295-115">Строка, содержащая имя контракта.</span><span class="sxs-lookup"><span data-stu-id="ec295-115">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="ec295-116">namespace</span><span class="sxs-lookup"><span data-stu-id="ec295-116">namespace</span></span>|<span data-ttu-id="ec295-117">Строка, содержащая пространство имен контракта.</span><span class="sxs-lookup"><span data-stu-id="ec295-117">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="ec295-118">requiresSession</span><span class="sxs-lookup"><span data-stu-id="ec295-118">requiresSession</span></span>|<span data-ttu-id="ec295-119">Логическое значение, указывающее, ограничено ли использование контракта только сеансовыми привязками.</span><span class="sxs-lookup"><span data-stu-id="ec295-119">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="ec295-120">При инициализации службы среда выполнения интеграции обеспечивает согласованность этого параметра с типом используемой привязки.</span><span class="sxs-lookup"><span data-stu-id="ec295-120">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="ec295-121">В случае конфликта одной или нескольких привязок для контракта создается исключение.</span><span class="sxs-lookup"><span data-stu-id="ec295-121">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="ec295-122">Если это свойство имеет значение `false`, то при использовании одностороннего канала и наличии параметров [out] также создается исключение.</span><span class="sxs-lookup"><span data-stu-id="ec295-122">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec295-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ec295-123">Child Elements</span></span>  
  
|<span data-ttu-id="ec295-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec295-124">Element</span></span>|<span data-ttu-id="ec295-125">Описание</span><span class="sxs-lookup"><span data-stu-id="ec295-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec295-126">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="ec295-126">persistableTypes</span></span>|<span data-ttu-id="ec295-127">Все сохраняемые типы.</span><span class="sxs-lookup"><span data-stu-id="ec295-127">All the persistable types.</span></span>|  
|<span data-ttu-id="ec295-128">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="ec295-128">userDefinedTypes</span></span>|<span data-ttu-id="ec295-129">Коллекция пользовательских типов (UDT), подлежащая включению в контракт службы.</span><span class="sxs-lookup"><span data-stu-id="ec295-129">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="ec295-130">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="ec295-130">exposedMethods</span></span>|<span data-ttu-id="ec295-131">Коллекция методов COM+, которые предоставляются при предоставлении интерфейса компонента COM+ как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="ec295-131">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ec295-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ec295-132">Parent Elements</span></span>  
  
|<span data-ttu-id="ec295-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec295-133">Element</span></span>|<span data-ttu-id="ec295-134">Описание</span><span class="sxs-lookup"><span data-stu-id="ec295-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec295-135">comContracts</span><span class="sxs-lookup"><span data-stu-id="ec295-135">comContracts</span></span>|<span data-ttu-id="ec295-136">Содержит коллекцию элементов `comContract`.</span><span class="sxs-lookup"><span data-stu-id="ec295-136">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec295-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="ec295-137">Remarks</span></span>  
 <span data-ttu-id="ec295-138">Контракты службы интеграции COM +, в настоящее время ограничены `http://tempuri.org` пространства имен, а имя контракта является производным от поддерживающего COM-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ec295-138">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="ec295-139">Однако можно указать альтернативы, используя раздел `comContracts`, а также элемент `comContract` в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ec295-139">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="ec295-140">Например, для указания пространства имен, имени контракта и подлежащих включению пользовательских типов, а также других параметров контракта службы можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="ec295-140">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="ec295-141">После инициализации службы указанные пространства имен и имена контрактов применяются к созданным описаниям служб.</span><span class="sxs-lookup"><span data-stu-id="ec295-141">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec295-142">См. также</span><span class="sxs-lookup"><span data-stu-id="ec295-142">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="ec295-143">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="ec295-143">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="ec295-144">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="ec295-144">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="ec295-145">Практическое руководство. Настройка параметров службы COM +</span><span class="sxs-lookup"><span data-stu-id="ec295-145">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
