---
title: Элемент <generatePublisherEvidence>
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: b04ef53d6e9c3d954b0925ea8634b3d220b36af7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116577"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="fda0b-102">\<generatePublisherEvidence > элемент</span><span class="sxs-lookup"><span data-stu-id="fda0b-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="fda0b-103">Указывает, создает ли среда выполнения <xref:System.Security.Policy.Publisher> свидетельство для управления доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="fda0b-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="fda0b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fda0b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fda0b-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="fda0b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="fda0b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<generatePublisherEvidence >**</span><span class="sxs-lookup"><span data-stu-id="fda0b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fda0b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fda0b-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fda0b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fda0b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fda0b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fda0b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fda0b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fda0b-110">Attributes</span></span>  
  
|<span data-ttu-id="fda0b-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fda0b-111">Attribute</span></span>|<span data-ttu-id="fda0b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fda0b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="fda0b-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="fda0b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="fda0b-114">Указывает, создает ли среда выполнения <xref:System.Security.Policy.Publisher> свидетельство.</span><span class="sxs-lookup"><span data-stu-id="fda0b-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="fda0b-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="fda0b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="fda0b-116">значения</span><span class="sxs-lookup"><span data-stu-id="fda0b-116">Value</span></span>|<span data-ttu-id="fda0b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="fda0b-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="fda0b-118">Не создает <xref:System.Security.Policy.Publisher> свидетельство.</span><span class="sxs-lookup"><span data-stu-id="fda0b-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="fda0b-119">Создает <xref:System.Security.Policy.Publisher> свидетельство.</span><span class="sxs-lookup"><span data-stu-id="fda0b-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="fda0b-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fda0b-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fda0b-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fda0b-121">Child Elements</span></span>  
 <span data-ttu-id="fda0b-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fda0b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fda0b-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fda0b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fda0b-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="fda0b-124">Element</span></span>|<span data-ttu-id="fda0b-125">Описание</span><span class="sxs-lookup"><span data-stu-id="fda0b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fda0b-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fda0b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fda0b-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="fda0b-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fda0b-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="fda0b-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fda0b-129">В .NET Framework 4 и более поздних версиях этот элемент не влияет на время загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="fda0b-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="fda0b-130">Дополнительные сведения см. в разделе "упрощение политики безопасности" раздела [изменения в системе безопасности](../../../security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="fda0b-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="fda0b-131">Среда CLR пытается проверить подпись Authenticode во время загрузки, чтобы создать <xref:System.Security.Policy.Publisher> свидетельство для сборки.</span><span class="sxs-lookup"><span data-stu-id="fda0b-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="fda0b-132">Однако по умолчанию большинству приложений не требуется <xref:System.Security.Policy.Publisher> свидетельство.</span><span class="sxs-lookup"><span data-stu-id="fda0b-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="fda0b-133">Стандартная политика CAS не зависит от <xref:System.Security.Policy.PublisherMembershipCondition>.</span><span class="sxs-lookup"><span data-stu-id="fda0b-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="fda0b-134">Следует избегать ненужных затрат на запуск, связанных с проверкой подписи издателя, если приложение не выполняется на компьютере с настраиваемой политикой CAS или планирует удовлетворить требования к <xref:System.Security.Permissions.PublisherIdentityPermission> в среде с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="fda0b-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="fda0b-135">(Требования для разрешений идентификации всегда выполняются в среде с полным доверием.)</span><span class="sxs-lookup"><span data-stu-id="fda0b-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fda0b-136">Для повышения производительности при запуске службы рекомендуется использовать элемент `<generatePublisherEvidence>`.</span><span class="sxs-lookup"><span data-stu-id="fda0b-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="fda0b-137">Использование этого элемента также может помочь избежать задержек, которые могут привести к превышению времени ожидания и отмене запуска службы.</span><span class="sxs-lookup"><span data-stu-id="fda0b-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="fda0b-138">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="fda0b-138">Configuration File</span></span>  
 <span data-ttu-id="fda0b-139">Этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="fda0b-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fda0b-140">Пример</span><span class="sxs-lookup"><span data-stu-id="fda0b-140">Example</span></span>  
 <span data-ttu-id="fda0b-141">В следующем примере показано, как использовать элемент `<generatePublisherEvidence>`, чтобы отключить проверку политики издателя CAS для приложения.</span><span class="sxs-lookup"><span data-stu-id="fda0b-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fda0b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="fda0b-142">See also</span></span>

- [<span data-ttu-id="fda0b-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="fda0b-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fda0b-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="fda0b-144">Configuration File Schema</span></span>](../index.md)
