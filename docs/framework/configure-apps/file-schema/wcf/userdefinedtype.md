---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: 46beb88cedf051ed1683161b6ed9b37273ed01f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182145"
---
# <a name="userdefinedtype"></a><span data-ttu-id="e7f08-101">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="e7f08-101">\<userDefinedType></span></span>
<span data-ttu-id="e7f08-102">Представляет определяемый пользователем тип (UDT), подлежащий включению в контракт службы.</span><span class="sxs-lookup"><span data-stu-id="e7f08-102">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
 <span data-ttu-id="e7f08-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e7f08-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e7f08-104">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="e7f08-104">\<comContracts></span></span>  
<span data-ttu-id="e7f08-105">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="e7f08-105">\<comContract></span></span>  
<span data-ttu-id="e7f08-106">\<userDefinedTypes></span><span class="sxs-lookup"><span data-stu-id="e7f08-106">\<userDefinedTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f08-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7f08-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7f08-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e7f08-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e7f08-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e7f08-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7f08-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7f08-110">Attributes</span></span>  
  
|<span data-ttu-id="e7f08-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e7f08-111">Attribute</span></span>|<span data-ttu-id="e7f08-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e7f08-112">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="e7f08-113">Необязательный атрибут, содержащий строку, которая задает отображаемое имя типа.</span><span class="sxs-lookup"><span data-stu-id="e7f08-113">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="e7f08-114">Не используется средой выполнения, но помогает читателю различать типы.</span><span class="sxs-lookup"><span data-stu-id="e7f08-114">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="e7f08-115">Строка идентификатора GUID, которая идентифицирует конкретный тип UDT в зарегистрированной библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="e7f08-115">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="e7f08-116">Срока глобального уникального идентификатора (GUID), которая является идентификатором для зарегистрированной библиотеки типов, определяющей тип.</span><span class="sxs-lookup"><span data-stu-id="e7f08-116">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="e7f08-117">Срока, которая является идентификатором версии библиотеки типов, определяющей тип.</span><span class="sxs-lookup"><span data-stu-id="e7f08-117">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7f08-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7f08-118">Child Elements</span></span>  
 <span data-ttu-id="e7f08-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e7f08-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7f08-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e7f08-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e7f08-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7f08-121">Element</span></span>|<span data-ttu-id="e7f08-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e7f08-122">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="e7f08-123">Коллекция элементов `userDefinedType`.</span><span class="sxs-lookup"><span data-stu-id="e7f08-123">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7f08-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7f08-124">Remarks</span></span>  
 <span data-ttu-id="e7f08-125">Среда выполнения интеграции СОМ+ создает службы путем проверки библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="e7f08-125">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="e7f08-126">Если в компоненте СОМ+ содержатся методы, которые служат для передачи VARIANT, система не в состоянии определить фактические типы для передачи до среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e7f08-126">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="e7f08-127">Поэтому при попытке передать пользовательский тип (UDT) в рамках VARIANT происходит сбой, поскольку данный тип не является известным типом для сериализации.</span><span class="sxs-lookup"><span data-stu-id="e7f08-127">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="e7f08-128">Для решения этой проблемы можно добавить пользовательские типы в файл конфигурации, чтобы их можно было включить как известные типы в соответствующий контракт службы.</span><span class="sxs-lookup"><span data-stu-id="e7f08-128">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="e7f08-129">Для этого необходимо однозначно определить пользовательский тип и контракты, то есть исходные интерфейсы СОМ, которые его используют.</span><span class="sxs-lookup"><span data-stu-id="e7f08-129">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="e7f08-130">В следующем примере показано добавление два конкретных пользовательских типа <`userDefinedTypes`> раздел файла конфигурации для этой цели.</span><span class="sxs-lookup"><span data-stu-id="e7f08-130">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
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
  
 <span data-ttu-id="e7f08-131">При запуске службы среда выполнения интеграции выполняет поиск по указанным типам и добавляет их в коллекции известных типов для заданных контрактов.</span><span class="sxs-lookup"><span data-stu-id="e7f08-131">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7f08-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e7f08-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [<span data-ttu-id="e7f08-133">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="e7f08-133">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="e7f08-134">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="e7f08-134">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="e7f08-135">Практическое руководство. Настройка параметров службы COM +</span><span class="sxs-lookup"><span data-stu-id="e7f08-135">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
