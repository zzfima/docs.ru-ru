---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: 7a76e5a90fe3218bc0302501b71daa9de0b098bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854835"
---
# <a name="userdefinedtype"></a><span data-ttu-id="b39e2-101">\<userDefinedType ></span><span class="sxs-lookup"><span data-stu-id="b39e2-101">\<userDefinedType></span></span>
<span data-ttu-id="b39e2-102">Представляет определяемый пользователем тип (UDT), подлежащий включению в контракт службы.</span><span class="sxs-lookup"><span data-stu-id="b39e2-102">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
<span data-ttu-id="b39e2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b39e2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b39e2-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b39e2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b39e2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="b39e2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="b39e2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Комконтракт >** ](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="b39e2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="b39e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Усердефинедтипес >** ](userdefinedtypes.md)</span><span class="sxs-lookup"><span data-stu-id="b39e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<userDefinedTypes>**](userdefinedtypes.md)</span></span>\
<span data-ttu-id="b39e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userDefinedType >**</span><span class="sxs-lookup"><span data-stu-id="b39e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userDefinedType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b39e2-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b39e2-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b39e2-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b39e2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b39e2-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b39e2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b39e2-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b39e2-112">Attributes</span></span>  
  
|<span data-ttu-id="b39e2-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b39e2-113">Attribute</span></span>|<span data-ttu-id="b39e2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b39e2-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b39e2-115">Необязательный атрибут, содержащий строку, которая задает отображаемое имя типа.</span><span class="sxs-lookup"><span data-stu-id="b39e2-115">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="b39e2-116">Не используется средой выполнения, но помогает читателю различать типы.</span><span class="sxs-lookup"><span data-stu-id="b39e2-116">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="b39e2-117">Строка идентификатора GUID, которая идентифицирует конкретный тип UDT в зарегистрированной библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="b39e2-117">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="b39e2-118">Срока глобального уникального идентификатора (GUID), которая является идентификатором для зарегистрированной библиотеки типов, определяющей тип.</span><span class="sxs-lookup"><span data-stu-id="b39e2-118">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="b39e2-119">Срока, которая является идентификатором версии библиотеки типов, определяющей тип.</span><span class="sxs-lookup"><span data-stu-id="b39e2-119">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b39e2-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b39e2-120">Child Elements</span></span>  
 <span data-ttu-id="b39e2-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="b39e2-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b39e2-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b39e2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b39e2-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="b39e2-123">Element</span></span>|<span data-ttu-id="b39e2-124">Описание</span><span class="sxs-lookup"><span data-stu-id="b39e2-124">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="b39e2-125">Коллекция элементов `userDefinedType`.</span><span class="sxs-lookup"><span data-stu-id="b39e2-125">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b39e2-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="b39e2-126">Remarks</span></span>  
 <span data-ttu-id="b39e2-127">Среда выполнения интеграции СОМ+ создает службы путем проверки библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="b39e2-127">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="b39e2-128">Если в компоненте СОМ+ содержатся методы, которые служат для передачи VARIANT, система не в состоянии определить фактические типы для передачи до среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b39e2-128">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="b39e2-129">Поэтому при попытке передать пользовательский тип (UDT) в рамках VARIANT происходит сбой, поскольку данный тип не является известным типом для сериализации.</span><span class="sxs-lookup"><span data-stu-id="b39e2-129">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="b39e2-130">Для решения этой проблемы можно добавить пользовательские типы в файл конфигурации, чтобы их можно было включить как известные типы в соответствующий контракт службы.</span><span class="sxs-lookup"><span data-stu-id="b39e2-130">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="b39e2-131">Для этого необходимо однозначно определить пользовательский тип и контракты, то есть исходные интерфейсы СОМ, которые его используют.</span><span class="sxs-lookup"><span data-stu-id="b39e2-131">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="b39e2-132">В следующем примере показано добавление двух специальных определяемых пользователем типов`userDefinedTypes`в раздел < > файла конфигурации для этой цели.</span><span class="sxs-lookup"><span data-stu-id="b39e2-132">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <userDefinedTypes>
      <userDefinedType name="CustomerType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{D129765C-F211-434e-825A-9A63198C41F2}">
      </userDefinedType>
      <userDefinedType name="AddressType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{4616AE0D-687A-43B7-BC63-141AE3DFD099}">
      </userDefinedType>
    </userDefinedTypes>
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="b39e2-133">При запуске службы среда выполнения интеграции выполняет поиск по указанным типам и добавляет их в коллекции известных типов для заданных контрактов.</span><span class="sxs-lookup"><span data-stu-id="b39e2-133">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b39e2-134">См. также</span><span class="sxs-lookup"><span data-stu-id="b39e2-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [<span data-ttu-id="b39e2-135">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="b39e2-135">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="b39e2-136">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="b39e2-136">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="b39e2-137">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="b39e2-137">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
