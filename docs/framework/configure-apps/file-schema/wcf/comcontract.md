---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 8694f83a731363f83cb09de43214eb4b211ef5ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704288"
---
# <a name="comcontract"></a><span data-ttu-id="8bf5f-101">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="8bf5f-101">\<comContract></span></span>
<span data-ttu-id="8bf5f-102">Указывает контракт службы интеграции COM+.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-102">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="8bf5f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8bf5f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8bf5f-104">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="8bf5f-104">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bf5f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bf5f-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bf5f-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8bf5f-106">Attributes and Elements</span></span>  
 <span data-ttu-id="8bf5f-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bf5f-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8bf5f-108">Attributes</span></span>  
  
|<span data-ttu-id="8bf5f-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8bf5f-109">Attribute</span></span>|<span data-ttu-id="8bf5f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="8bf5f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bf5f-111">контракт</span><span class="sxs-lookup"><span data-stu-id="8bf5f-111">contract</span></span>|<span data-ttu-id="8bf5f-112">Строка, содержащая тип контракта.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-112">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="8bf5f-113">имя</span><span class="sxs-lookup"><span data-stu-id="8bf5f-113">name</span></span>|<span data-ttu-id="8bf5f-114">Строка, содержащая имя контракта.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-114">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="8bf5f-115">namespace</span><span class="sxs-lookup"><span data-stu-id="8bf5f-115">namespace</span></span>|<span data-ttu-id="8bf5f-116">Строка, содержащая пространство имен контракта.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-116">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="8bf5f-117">requiresSession</span><span class="sxs-lookup"><span data-stu-id="8bf5f-117">requiresSession</span></span>|<span data-ttu-id="8bf5f-118">Логическое значение, указывающее, ограничено ли использование контракта только сеансовыми привязками.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-118">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="8bf5f-119">При инициализации службы среда выполнения интеграции обеспечивает согласованность этого параметра с типом используемой привязки.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-119">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="8bf5f-120">В случае конфликта одной или нескольких привязок для контракта создается исключение.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-120">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="8bf5f-121">Если это свойство имеет значение `false`, то при использовании одностороннего канала и наличии параметров [out] также создается исключение.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-121">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8bf5f-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8bf5f-122">Child Elements</span></span>  
  
|<span data-ttu-id="8bf5f-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="8bf5f-123">Element</span></span>|<span data-ttu-id="8bf5f-124">Описание</span><span class="sxs-lookup"><span data-stu-id="8bf5f-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8bf5f-125">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="8bf5f-125">persistableTypes</span></span>|<span data-ttu-id="8bf5f-126">Все сохраняемые типы.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-126">All the persistable types.</span></span>|  
|<span data-ttu-id="8bf5f-127">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="8bf5f-127">userDefinedTypes</span></span>|<span data-ttu-id="8bf5f-128">Коллекция пользовательских типов (UDT), подлежащая включению в контракт службы.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-128">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="8bf5f-129">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="8bf5f-129">exposedMethods</span></span>|<span data-ttu-id="8bf5f-130">Коллекция методов COM+, которые предоставляются при предоставлении интерфейса компонента COM+ как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-130">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8bf5f-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8bf5f-131">Parent Elements</span></span>  
  
|<span data-ttu-id="8bf5f-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="8bf5f-132">Element</span></span>|<span data-ttu-id="8bf5f-133">Описание</span><span class="sxs-lookup"><span data-stu-id="8bf5f-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8bf5f-134">comContracts</span><span class="sxs-lookup"><span data-stu-id="8bf5f-134">comContracts</span></span>|<span data-ttu-id="8bf5f-135">Содержит коллекцию элементов `comContract`.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-135">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bf5f-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="8bf5f-136">Remarks</span></span>  
 <span data-ttu-id="8bf5f-137">Контракты службы интеграции COM +, в настоящее время ограничены `http://tempuri.org` пространства имен, а имя контракта является производным от поддерживающего COM-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-137">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="8bf5f-138">Однако можно указать альтернативы, используя раздел `comContracts`, а также элемент `comContract` в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-138">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="8bf5f-139">Например, для указания пространства имен, имени контракта и подлежащих включению пользовательских типов, а также других параметров контракта службы можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-139">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="8bf5f-140">После инициализации службы указанные пространства имен и имена контрактов применяются к созданным описаниям служб.</span><span class="sxs-lookup"><span data-stu-id="8bf5f-140">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf5f-141">См. также</span><span class="sxs-lookup"><span data-stu-id="8bf5f-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="8bf5f-142">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="8bf5f-142">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="8bf5f-143">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="8bf5f-143">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="8bf5f-144">Практическое руководство. Настройка параметров службы COM +</span><span class="sxs-lookup"><span data-stu-id="8bf5f-144">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
