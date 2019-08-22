---
title: Элемент <generatePublisherEvidence>
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caec297f8d0f6febad5cf46adb0a2658960c6bb1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663674"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="84694-102">\<Элемент > generatePublisherEvidence</span><span class="sxs-lookup"><span data-stu-id="84694-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="84694-103">Указывает, создает <xref:System.Security.Policy.Publisher> ли среда выполнения свидетельство для управления доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="84694-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="84694-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="84694-104">\<configuration></span></span>  
<span data-ttu-id="84694-105">\<> среды выполнения</span><span class="sxs-lookup"><span data-stu-id="84694-105">\<runtime></span></span>  
<span data-ttu-id="84694-106">\<generatePublisherEvidence ></span><span class="sxs-lookup"><span data-stu-id="84694-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84694-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84694-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84694-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="84694-108">Attributes and Elements</span></span>  
 <span data-ttu-id="84694-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="84694-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84694-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="84694-110">Attributes</span></span>  
  
|<span data-ttu-id="84694-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="84694-111">Attribute</span></span>|<span data-ttu-id="84694-112">Описание</span><span class="sxs-lookup"><span data-stu-id="84694-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="84694-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="84694-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="84694-114">Указывает, создает <xref:System.Security.Policy.Publisher> ли среда выполнения свидетельство.</span><span class="sxs-lookup"><span data-stu-id="84694-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="84694-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="84694-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="84694-116">Значение</span><span class="sxs-lookup"><span data-stu-id="84694-116">Value</span></span>|<span data-ttu-id="84694-117">Описание</span><span class="sxs-lookup"><span data-stu-id="84694-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="84694-118">Не создает <xref:System.Security.Policy.Publisher> свидетельство.</span><span class="sxs-lookup"><span data-stu-id="84694-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="84694-119">Создает <xref:System.Security.Policy.Publisher> свидетельство.</span><span class="sxs-lookup"><span data-stu-id="84694-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="84694-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="84694-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84694-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="84694-121">Child Elements</span></span>  
 <span data-ttu-id="84694-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="84694-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84694-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="84694-123">Parent Elements</span></span>  
  
|<span data-ttu-id="84694-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="84694-124">Element</span></span>|<span data-ttu-id="84694-125">Описание</span><span class="sxs-lookup"><span data-stu-id="84694-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="84694-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="84694-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="84694-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="84694-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84694-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="84694-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84694-129">В .NET Framework 4 и более поздних версиях этот элемент не влияет на время загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="84694-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="84694-130">Дополнительные сведения см. в разделе "упрощение политики безопасности" раздела [изменения в системе безопасности](../../../security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="84694-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="84694-131">Среда CLR пытается проверить подпись Authenticode во время загрузки, чтобы создать <xref:System.Security.Policy.Publisher> свидетельство для сборки.</span><span class="sxs-lookup"><span data-stu-id="84694-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="84694-132">Однако по умолчанию большинству приложений не требуется <xref:System.Security.Policy.Publisher> свидетельство.</span><span class="sxs-lookup"><span data-stu-id="84694-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="84694-133">Стандартная политика CAS не зависит от <xref:System.Security.Policy.PublisherMembershipCondition>.</span><span class="sxs-lookup"><span data-stu-id="84694-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="84694-134">Следует избегать ненужных затрат на запуск, связанных с проверкой подписи издателя, если приложение не выполняется на компьютере с настраиваемой политикой CAS или планирует удовлетворить требования <xref:System.Security.Permissions.PublisherIdentityPermission> к в среде с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="84694-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="84694-135">(Требования для разрешений идентификации всегда выполняются в среде с полным доверием.)</span><span class="sxs-lookup"><span data-stu-id="84694-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84694-136">Рекомендуется, чтобы службы использовали `<generatePublisherEvidence>` элемент для повышения производительности при запуске.</span><span class="sxs-lookup"><span data-stu-id="84694-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="84694-137">Использование этого элемента также может помочь избежать задержек, которые могут привести к превышению времени ожидания и отмене запуска службы.</span><span class="sxs-lookup"><span data-stu-id="84694-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="84694-138">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="84694-138">Configuration File</span></span>  
 <span data-ttu-id="84694-139">Этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="84694-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84694-140">Пример</span><span class="sxs-lookup"><span data-stu-id="84694-140">Example</span></span>  
 <span data-ttu-id="84694-141">В следующем примере показано, как использовать `<generatePublisherEvidence>` элемент, чтобы отключить проверку политики издателя CAS для приложения.</span><span class="sxs-lookup"><span data-stu-id="84694-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="84694-142">См. также</span><span class="sxs-lookup"><span data-stu-id="84694-142">See also</span></span>

- [<span data-ttu-id="84694-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="84694-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="84694-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="84694-144">Configuration File Schema</span></span>](../index.md)
