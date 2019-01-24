---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9292a0973df100acbffa341d7c0ca2604455f7fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522340"
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a><span data-ttu-id="9972c-102">&lt;PreferComInsteadOfManagedRemoting&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="9972c-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span></span>
<span data-ttu-id="9972c-103">Указывает, использует ли среда выполнения COM-взаимодействие вместо удаленного взаимодействия для всех вызовов через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="9972c-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="9972c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9972c-104">\<configuration></span></span>  
<span data-ttu-id="9972c-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="9972c-105">\<runtime></span></span>  
<span data-ttu-id="9972c-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="9972c-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9972c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9972c-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9972c-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9972c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9972c-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9972c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9972c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9972c-110">Attributes</span></span>  
  
|<span data-ttu-id="9972c-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9972c-111">Attribute</span></span>|<span data-ttu-id="9972c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9972c-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9972c-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9972c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9972c-114">Указывает ли среда выполнения будет использовать COM-взаимодействие вместо удаленного взаимодействия через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="9972c-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9972c-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="9972c-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9972c-116">Значение</span><span class="sxs-lookup"><span data-stu-id="9972c-116">Value</span></span>|<span data-ttu-id="9972c-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="9972c-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9972c-118">Среда выполнения будет использовать удаленное взаимодействие через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="9972c-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="9972c-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9972c-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="9972c-120">Среда выполнения будет использовать COM-взаимодействия через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="9972c-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9972c-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9972c-121">Child Elements</span></span>  
 <span data-ttu-id="9972c-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9972c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9972c-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9972c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9972c-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="9972c-124">Element</span></span>|<span data-ttu-id="9972c-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="9972c-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9972c-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9972c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9972c-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="9972c-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9972c-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="9972c-128">Remarks</span></span>  
 <span data-ttu-id="9972c-129">При задании `enabled` атрибут `true`, среда выполнения ведет себя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9972c-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="9972c-130">Среда выполнения не вызывает [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) для [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) Если интерфейс [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) интерфейс входит в домен через COM-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9972c-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="9972c-131">Вместо этого она создает [вызываемой оболочки времени выполнения](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) вокруг объекта.</span><span class="sxs-lookup"><span data-stu-id="9972c-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="9972c-132">Среда выполнения возвращает E_NOINTERFACE при получении `QueryInterface` вызова для [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) интерфейс для любого [вызываемая оболочка COM](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) который был создан в этом домене.</span><span class="sxs-lookup"><span data-stu-id="9972c-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="9972c-133">Эти два поведения гарантируют, что все вызовы через COM-интерфейсы между управляемыми объектами через границы домена приложения используют COM и COM-взаимодействие вместо удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9972c-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9972c-134">Пример</span><span class="sxs-lookup"><span data-stu-id="9972c-134">Example</span></span>  
 <span data-ttu-id="9972c-135">В следующем примере показано, как указать, что среда выполнения должна использовать COM-взаимодействия через границы изоляции:</span><span class="sxs-lookup"><span data-stu-id="9972c-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9972c-136">См. также</span><span class="sxs-lookup"><span data-stu-id="9972c-136">See also</span></span>
- [<span data-ttu-id="9972c-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="9972c-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="9972c-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="9972c-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
