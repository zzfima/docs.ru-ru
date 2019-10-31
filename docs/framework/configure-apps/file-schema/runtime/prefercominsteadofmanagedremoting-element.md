---
title: Элемент <PreferComInsteadOfManagedRemoting>
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 47c568a8d6e89a195414552b3db5953ee61d1e55
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116020"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="00ecb-102">\<Преферкоминстеадофманажедремотинг > элемент</span><span class="sxs-lookup"><span data-stu-id="00ecb-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="00ecb-103">Указывает, будет ли среда выполнения использовать COM-взаимодействие вместо удаленного взаимодействия для всех вызовов через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="00ecb-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
<span data-ttu-id="00ecb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00ecb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00ecb-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="00ecb-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="00ecb-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<преферкоминстеадофманажедремотинг >**</span><span class="sxs-lookup"><span data-stu-id="00ecb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00ecb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00ecb-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00ecb-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="00ecb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="00ecb-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="00ecb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00ecb-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="00ecb-110">Attributes</span></span>  
  
|<span data-ttu-id="00ecb-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="00ecb-111">Attribute</span></span>|<span data-ttu-id="00ecb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="00ecb-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="00ecb-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="00ecb-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="00ecb-114">Указывает, будет ли среда выполнения использовать COM-взаимодействие вместо удаленного взаимодействия через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="00ecb-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="00ecb-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="00ecb-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="00ecb-116">значения</span><span class="sxs-lookup"><span data-stu-id="00ecb-116">Value</span></span>|<span data-ttu-id="00ecb-117">Описание</span><span class="sxs-lookup"><span data-stu-id="00ecb-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="00ecb-118">Среда выполнения будет использовать удаленное взаимодействие через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="00ecb-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="00ecb-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00ecb-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="00ecb-120">Среда выполнения будет использовать COM-взаимодействие через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="00ecb-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00ecb-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="00ecb-121">Child Elements</span></span>  
 <span data-ttu-id="00ecb-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="00ecb-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00ecb-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="00ecb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="00ecb-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="00ecb-124">Element</span></span>|<span data-ttu-id="00ecb-125">Описание</span><span class="sxs-lookup"><span data-stu-id="00ecb-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="00ecb-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00ecb-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="00ecb-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="00ecb-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00ecb-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="00ecb-128">Remarks</span></span>  
 <span data-ttu-id="00ecb-129">Если для атрибута `enabled` задано значение `true`, среда выполнения ведет себя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="00ecb-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="00ecb-130">Среда выполнения не вызывает [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) для интерфейса [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) , когда интерфейс [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) входит в домен через интерфейс COM.</span><span class="sxs-lookup"><span data-stu-id="00ecb-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="00ecb-131">Вместо этого он формирует [вызываемую оболочку времени выполнения](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) вокруг объекта.</span><span class="sxs-lookup"><span data-stu-id="00ecb-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="00ecb-132">Среда выполнения возвращает E_NOINTERFACE при получении вызова `QueryInterface` для интерфейса [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) для любой [вызываемой оболочки COM](../../../../standard/native-interop/com-callable-wrapper.md) (CCW), созданной в этом домене.</span><span class="sxs-lookup"><span data-stu-id="00ecb-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="00ecb-133">Эти два поведения гарантируют, что все вызовы через COM-интерфейсы между управляемыми объектами в границах доменов приложений используют COM и COM-взаимодействие вместо удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="00ecb-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00ecb-134">Пример</span><span class="sxs-lookup"><span data-stu-id="00ecb-134">Example</span></span>  
 <span data-ttu-id="00ecb-135">В следующем примере показано, как указать, что среда выполнения должна использовать COM-взаимодействие через границы изоляции:</span><span class="sxs-lookup"><span data-stu-id="00ecb-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="00ecb-136">См. также</span><span class="sxs-lookup"><span data-stu-id="00ecb-136">See also</span></span>

- [<span data-ttu-id="00ecb-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="00ecb-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="00ecb-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="00ecb-138">Configuration File Schema</span></span>](../index.md)
