---
title: Элемент <PreferComInsteadOfManagedRemoting>
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a71c2b87d0bcb488e4e8fa4de928a103a8e9dabd
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663544"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="53b4b-102">\<Элемент > Преферкоминстеадофманажедремотинг</span><span class="sxs-lookup"><span data-stu-id="53b4b-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="53b4b-103">Указывает, будет ли среда выполнения использовать COM-взаимодействие вместо удаленного взаимодействия для всех вызовов через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="53b4b-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="53b4b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="53b4b-104">\<configuration></span></span>  
<span data-ttu-id="53b4b-105">\<> среды выполнения</span><span class="sxs-lookup"><span data-stu-id="53b4b-105">\<runtime></span></span>  
<span data-ttu-id="53b4b-106">\<Преферкоминстеадофманажедремотинг ></span><span class="sxs-lookup"><span data-stu-id="53b4b-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53b4b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53b4b-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53b4b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="53b4b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="53b4b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="53b4b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53b4b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="53b4b-110">Attributes</span></span>  
  
|<span data-ttu-id="53b4b-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="53b4b-111">Attribute</span></span>|<span data-ttu-id="53b4b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="53b4b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="53b4b-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="53b4b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="53b4b-114">Указывает, будет ли среда выполнения использовать COM-взаимодействие вместо удаленного взаимодействия через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="53b4b-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="53b4b-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="53b4b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="53b4b-116">Значение</span><span class="sxs-lookup"><span data-stu-id="53b4b-116">Value</span></span>|<span data-ttu-id="53b4b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="53b4b-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="53b4b-118">Среда выполнения будет использовать удаленное взаимодействие через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="53b4b-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="53b4b-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="53b4b-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="53b4b-120">Среда выполнения будет использовать COM-взаимодействие через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="53b4b-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53b4b-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="53b4b-121">Child Elements</span></span>  
 <span data-ttu-id="53b4b-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="53b4b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53b4b-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="53b4b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="53b4b-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="53b4b-124">Element</span></span>|<span data-ttu-id="53b4b-125">Описание</span><span class="sxs-lookup"><span data-stu-id="53b4b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="53b4b-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="53b4b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="53b4b-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="53b4b-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53b4b-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="53b4b-128">Remarks</span></span>  
 <span data-ttu-id="53b4b-129">Если для `enabled` `true`атрибута задано значение, среда выполнения ведет себя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="53b4b-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="53b4b-130">Среда выполнения не вызывает [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) для интерфейса [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) , когда интерфейс [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) входит в домен через интерфейс COM.</span><span class="sxs-lookup"><span data-stu-id="53b4b-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="53b4b-131">Вместо этого он формирует вызываемую [оболочку времени выполнения](../../../../../docs/standard/native-interop/runtime-callable-wrapper.md) (RCW) вокруг объекта.</span><span class="sxs-lookup"><span data-stu-id="53b4b-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="53b4b-132">Среда выполнения возвращает E_NOINTERFACE при получении `QueryInterface` вызова для интерфейса [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) для любой вызываемой [оболочки COM](../../../../../docs/standard/native-interop/com-callable-wrapper.md) (CCW), созданной в этом домене.</span><span class="sxs-lookup"><span data-stu-id="53b4b-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="53b4b-133">Эти два поведения гарантируют, что все вызовы через COM-интерфейсы между управляемыми объектами в границах доменов приложений используют COM и COM-взаимодействие вместо удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="53b4b-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53b4b-134">Пример</span><span class="sxs-lookup"><span data-stu-id="53b4b-134">Example</span></span>  
 <span data-ttu-id="53b4b-135">В следующем примере показано, как указать, что среда выполнения должна использовать COM-взаимодействие через границы изоляции:</span><span class="sxs-lookup"><span data-stu-id="53b4b-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53b4b-136">См. также</span><span class="sxs-lookup"><span data-stu-id="53b4b-136">See also</span></span>

- [<span data-ttu-id="53b4b-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="53b4b-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="53b4b-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="53b4b-138">Configuration File Schema</span></span>](../index.md)
