---
title: Элемент <generatePublisherEvidence>
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a0861436ca727d63cdae58e3222826bf6414610
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489445"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="b4f85-102">\<generatePublisherEvidence > элемент</span><span class="sxs-lookup"><span data-stu-id="b4f85-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="b4f85-103">Указывает, является ли среда выполнения создает <xref:System.Security.Policy.Publisher> свидетельство для Управление доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="b4f85-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="b4f85-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b4f85-104">\<configuration></span></span>  
<span data-ttu-id="b4f85-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="b4f85-105">\<runtime></span></span>  
<span data-ttu-id="b4f85-106">\<generatePublisherEvidence></span><span class="sxs-lookup"><span data-stu-id="b4f85-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f85-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4f85-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4f85-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b4f85-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b4f85-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b4f85-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4f85-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b4f85-110">Attributes</span></span>  
  
|<span data-ttu-id="b4f85-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b4f85-111">Attribute</span></span>|<span data-ttu-id="b4f85-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b4f85-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b4f85-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b4f85-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b4f85-114">Указывает, является ли среда выполнения создает <xref:System.Security.Policy.Publisher> свидетельства.</span><span class="sxs-lookup"><span data-stu-id="b4f85-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b4f85-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="b4f85-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b4f85-116">Значение</span><span class="sxs-lookup"><span data-stu-id="b4f85-116">Value</span></span>|<span data-ttu-id="b4f85-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b4f85-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b4f85-118">Не создает <xref:System.Security.Policy.Publisher> свидетельства.</span><span class="sxs-lookup"><span data-stu-id="b4f85-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="b4f85-119">Создает <xref:System.Security.Policy.Publisher> свидетельства.</span><span class="sxs-lookup"><span data-stu-id="b4f85-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="b4f85-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b4f85-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4f85-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b4f85-121">Child Elements</span></span>  
 <span data-ttu-id="b4f85-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b4f85-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4f85-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b4f85-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b4f85-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="b4f85-124">Element</span></span>|<span data-ttu-id="b4f85-125">Описание</span><span class="sxs-lookup"><span data-stu-id="b4f85-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b4f85-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b4f85-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b4f85-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b4f85-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4f85-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="b4f85-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4f85-129">В .NET Framework 4 и более поздних версиях этот элемент не влияет на время загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="b4f85-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="b4f85-130">Дополнительные сведения см. в разделе «Упрощение политики безопасности» в [изменения системы безопасности](../../../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="b4f85-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="b4f85-131">Среда CLR (CLR) пытается проверить подпись Authenticode во время загрузки, чтобы создать <xref:System.Security.Policy.Publisher> свидетельство для сборки.</span><span class="sxs-lookup"><span data-stu-id="b4f85-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="b4f85-132">Тем не менее, по умолчанию, большинство приложений не обязательно <xref:System.Security.Policy.Publisher> свидетельства.</span><span class="sxs-lookup"><span data-stu-id="b4f85-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="b4f85-133">Стандартная политика CAS не зависит от <xref:System.Security.Policy.PublisherMembershipCondition>.</span><span class="sxs-lookup"><span data-stu-id="b4f85-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="b4f85-134">Следует избегать при запуске затраты, связанные с проверкой подписи издателя, если приложение выполняет на компьютере с нестандартной политики CAS, или собирается для <xref:System.Security.Permissions.PublisherIdentityPermission> в среде с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="b4f85-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="b4f85-135">(Для разрешения идентификаторов всегда удовлетворяются в среде с полным доверием.)</span><span class="sxs-lookup"><span data-stu-id="b4f85-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4f85-136">Мы рекомендуем, службы используют `<generatePublisherEvidence>` элемент для повышения производительности запуска.</span><span class="sxs-lookup"><span data-stu-id="b4f85-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="b4f85-137">С помощью этого элемента также может помочь избежать задержек, которые могут вызвать тайм-аута и отмене запуска службы.</span><span class="sxs-lookup"><span data-stu-id="b4f85-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="b4f85-138">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="b4f85-138">Configuration File</span></span>  
 <span data-ttu-id="b4f85-139">Этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b4f85-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4f85-140">Пример</span><span class="sxs-lookup"><span data-stu-id="b4f85-140">Example</span></span>  
 <span data-ttu-id="b4f85-141">В следующем примере показано, как использовать `<generatePublisherEvidence>` элемент, чтобы отключить проверку для издателя политику CAS для приложения.</span><span class="sxs-lookup"><span data-stu-id="b4f85-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4f85-142">См. также</span><span class="sxs-lookup"><span data-stu-id="b4f85-142">See also</span></span>

- [<span data-ttu-id="b4f85-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="b4f85-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="b4f85-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="b4f85-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
