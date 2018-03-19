---
title: '&lt;comContract&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8fa70ba3cf8e66411812b84821e80772c9930f7c
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2018
---
# <a name="ltcomcontractgt"></a><span data-ttu-id="573c8-102">&lt;comContract&gt;</span><span class="sxs-lookup"><span data-stu-id="573c8-102">&lt;comContract&gt;</span></span>
<span data-ttu-id="573c8-103">Указывает контракт службы интеграции COM+.</span><span class="sxs-lookup"><span data-stu-id="573c8-103">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="573c8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="573c8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="573c8-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="573c8-105">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="573c8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="573c8-106">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="string"  
      namespace="string"  
      name="string"  
      requireSession="Boolean">  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
      <userDefinedTypes>  
         <userDefinedType name="string"  
            typeLibID="string"  
            typeLibVersion="string"  
            typeDefID="string">  
         </userDefinedType>  
      </userDefinedTypes>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="573c8-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="573c8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="573c8-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="573c8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="573c8-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="573c8-109">Attributes</span></span>  
  
|<span data-ttu-id="573c8-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="573c8-110">Attribute</span></span>|<span data-ttu-id="573c8-111">Описание</span><span class="sxs-lookup"><span data-stu-id="573c8-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="573c8-112">контракт</span><span class="sxs-lookup"><span data-stu-id="573c8-112">contract</span></span>|<span data-ttu-id="573c8-113">Строка, содержащая тип контракта.</span><span class="sxs-lookup"><span data-stu-id="573c8-113">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="573c8-114">имя</span><span class="sxs-lookup"><span data-stu-id="573c8-114">name</span></span>|<span data-ttu-id="573c8-115">Строка, содержащая имя контракта.</span><span class="sxs-lookup"><span data-stu-id="573c8-115">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="573c8-116">namespace</span><span class="sxs-lookup"><span data-stu-id="573c8-116">namespace</span></span>|<span data-ttu-id="573c8-117">Строка, содержащая пространство имен контракта.</span><span class="sxs-lookup"><span data-stu-id="573c8-117">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="573c8-118">requiresSession</span><span class="sxs-lookup"><span data-stu-id="573c8-118">requiresSession</span></span>|<span data-ttu-id="573c8-119">Логическое значение, указывающее, ограничено ли использование контракта только сеансовыми привязками.</span><span class="sxs-lookup"><span data-stu-id="573c8-119">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="573c8-120">При инициализации службы среда выполнения интеграции обеспечивает согласованность этого параметра с типом используемой привязки.</span><span class="sxs-lookup"><span data-stu-id="573c8-120">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="573c8-121">В случае конфликта одной или нескольких привязок для контракта создается исключение.</span><span class="sxs-lookup"><span data-stu-id="573c8-121">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="573c8-122">Если это свойство имеет значение `false`, то при использовании одностороннего канала и наличии параметров [out] также создается исключение.</span><span class="sxs-lookup"><span data-stu-id="573c8-122">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="573c8-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="573c8-123">Child Elements</span></span>  
  
|<span data-ttu-id="573c8-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="573c8-124">Element</span></span>|<span data-ttu-id="573c8-125">Описание</span><span class="sxs-lookup"><span data-stu-id="573c8-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="573c8-126">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="573c8-126">persistableTypes</span></span>|<span data-ttu-id="573c8-127">Все сохраняемые типы.</span><span class="sxs-lookup"><span data-stu-id="573c8-127">All the persistable types.</span></span>|  
|<span data-ttu-id="573c8-128">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="573c8-128">userDefinedTypes</span></span>|<span data-ttu-id="573c8-129">Коллекция пользовательских типов (UDT), подлежащая включению в контракт службы.</span><span class="sxs-lookup"><span data-stu-id="573c8-129">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="573c8-130">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="573c8-130">exposedMethods</span></span>|<span data-ttu-id="573c8-131">Коллекция методов COM+, которые предоставляются при предоставлении интерфейса компонента COM+ как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="573c8-131">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="573c8-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="573c8-132">Parent Elements</span></span>  
  
|<span data-ttu-id="573c8-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="573c8-133">Element</span></span>|<span data-ttu-id="573c8-134">Описание</span><span class="sxs-lookup"><span data-stu-id="573c8-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="573c8-135">comContracts</span><span class="sxs-lookup"><span data-stu-id="573c8-135">comContracts</span></span>|<span data-ttu-id="573c8-136">Содержит коллекцию элементов `comContract`.</span><span class="sxs-lookup"><span data-stu-id="573c8-136">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="573c8-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="573c8-137">Remarks</span></span>  
 <span data-ttu-id="573c8-138">Контракты службы интеграции COM + в настоящее время ограничены "http://tempuri.org" пространство имен, а имя контракта является производным от поддерживающего COM-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="573c8-138">COM+ integration service contracts are currently restricted to the "http://tempuri.org" namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="573c8-139">Однако можно указать альтернативы, используя раздел `comContracts`, а также элемент `comContract` в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="573c8-139">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="573c8-140">Например, для указания пространства имен, имени контракта и подлежащих включению пользовательских типов, а также других параметров контракта службы можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="573c8-140">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
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
  
 <span data-ttu-id="573c8-141">После инициализации службы указанные пространства имен и имена контрактов применяются к созданным описаниям служб.</span><span class="sxs-lookup"><span data-stu-id="573c8-141">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="573c8-142">См. также</span><span class="sxs-lookup"><span data-stu-id="573c8-142">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="573c8-143">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="573c8-143">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="573c8-144">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="573c8-144">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="573c8-145">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="573c8-145">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
