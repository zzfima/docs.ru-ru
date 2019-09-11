---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: b499294af71ba230dcf985d4af1d013b1ca260cf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850031"
---
# <a name="comcontract"></a><span data-ttu-id="88720-101">\<Комконтракт ></span><span class="sxs-lookup"><span data-stu-id="88720-101">\<comContract></span></span>
<span data-ttu-id="88720-102">Указывает контракт службы интеграции COM+.</span><span class="sxs-lookup"><span data-stu-id="88720-102">Specifies a COM+ integration service contract.</span></span>  
  
<span data-ttu-id="88720-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="88720-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="88720-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="88720-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="88720-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="88720-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="88720-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Комконтракт >**</span><span class="sxs-lookup"><span data-stu-id="88720-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88720-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88720-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88720-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="88720-108">Attributes and Elements</span></span>  
 <span data-ttu-id="88720-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="88720-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88720-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="88720-110">Attributes</span></span>  
  
|<span data-ttu-id="88720-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="88720-111">Attribute</span></span>|<span data-ttu-id="88720-112">Описание</span><span class="sxs-lookup"><span data-stu-id="88720-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88720-113">контракт</span><span class="sxs-lookup"><span data-stu-id="88720-113">contract</span></span>|<span data-ttu-id="88720-114">Строка, содержащая тип контракта.</span><span class="sxs-lookup"><span data-stu-id="88720-114">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="88720-115">имя</span><span class="sxs-lookup"><span data-stu-id="88720-115">name</span></span>|<span data-ttu-id="88720-116">Строка, содержащая имя контракта.</span><span class="sxs-lookup"><span data-stu-id="88720-116">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="88720-117">namespace</span><span class="sxs-lookup"><span data-stu-id="88720-117">namespace</span></span>|<span data-ttu-id="88720-118">Строка, содержащая пространство имен контракта.</span><span class="sxs-lookup"><span data-stu-id="88720-118">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="88720-119">requiresSession</span><span class="sxs-lookup"><span data-stu-id="88720-119">requiresSession</span></span>|<span data-ttu-id="88720-120">Логическое значение, указывающее, ограничено ли использование контракта только сеансовыми привязками.</span><span class="sxs-lookup"><span data-stu-id="88720-120">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="88720-121">При инициализации службы среда выполнения интеграции обеспечивает согласованность этого параметра с типом используемой привязки.</span><span class="sxs-lookup"><span data-stu-id="88720-121">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="88720-122">В случае конфликта одной или нескольких привязок для контракта создается исключение.</span><span class="sxs-lookup"><span data-stu-id="88720-122">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="88720-123">Если это свойство имеет значение `false`, то при использовании одностороннего канала и наличии параметров [out] также создается исключение.</span><span class="sxs-lookup"><span data-stu-id="88720-123">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88720-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="88720-124">Child Elements</span></span>  
  
|<span data-ttu-id="88720-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="88720-125">Element</span></span>|<span data-ttu-id="88720-126">Описание</span><span class="sxs-lookup"><span data-stu-id="88720-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88720-127">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="88720-127">persistableTypes</span></span>|<span data-ttu-id="88720-128">Все сохраняемые типы.</span><span class="sxs-lookup"><span data-stu-id="88720-128">All the persistable types.</span></span>|  
|<span data-ttu-id="88720-129">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="88720-129">userDefinedTypes</span></span>|<span data-ttu-id="88720-130">Коллекция пользовательских типов (UDT), подлежащая включению в контракт службы.</span><span class="sxs-lookup"><span data-stu-id="88720-130">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="88720-131">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="88720-131">exposedMethods</span></span>|<span data-ttu-id="88720-132">Коллекция методов COM+, которые предоставляются при предоставлении интерфейса компонента COM+ как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="88720-132">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88720-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="88720-133">Parent Elements</span></span>  
  
|<span data-ttu-id="88720-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="88720-134">Element</span></span>|<span data-ttu-id="88720-135">Описание</span><span class="sxs-lookup"><span data-stu-id="88720-135">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88720-136">comContracts</span><span class="sxs-lookup"><span data-stu-id="88720-136">comContracts</span></span>|<span data-ttu-id="88720-137">Содержит коллекцию элементов `comContract`.</span><span class="sxs-lookup"><span data-stu-id="88720-137">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88720-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="88720-138">Remarks</span></span>  
 <span data-ttu-id="88720-139">Контракты службы интеграции COM+ в настоящее время ограничены `http://tempuri.org` пространством имен, а имя контракта является производным от поддерживающего com-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="88720-139">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="88720-140">Однако можно указать альтернативы, используя раздел `comContracts`, а также элемент `comContract` в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="88720-140">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="88720-141">Например, для указания пространства имен, имени контракта и подлежащих включению пользовательских типов, а также других параметров контракта службы можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="88720-141">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="88720-142">После инициализации службы указанные пространства имен и имена контрактов применяются к созданным описаниям служб.</span><span class="sxs-lookup"><span data-stu-id="88720-142">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88720-143">См. также</span><span class="sxs-lookup"><span data-stu-id="88720-143">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="88720-144">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="88720-144">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="88720-145">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="88720-145">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="88720-146">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="88720-146">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
