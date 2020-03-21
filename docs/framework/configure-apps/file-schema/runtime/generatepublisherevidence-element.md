---
title: Элемент <generatePublisherEvidence>
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 24a5ea02992a5bce681b5bab4fb7f75505bd225d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154118"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="99c61-102">\<Элемент generatePublisherEvidence></span><span class="sxs-lookup"><span data-stu-id="99c61-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="99c61-103">Уточняется, создает <xref:System.Security.Policy.Publisher> ли время выполнения доказательства безопасности доступа к коду (CAS).</span><span class="sxs-lookup"><span data-stu-id="99c61-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="99c61-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99c61-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99c61-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="99c61-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="99c61-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<генерироватьPublisherEvidence>**</span><span class="sxs-lookup"><span data-stu-id="99c61-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99c61-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99c61-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99c61-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="99c61-108">Attributes and Elements</span></span>  
 <span data-ttu-id="99c61-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="99c61-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99c61-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="99c61-110">Attributes</span></span>  
  
|<span data-ttu-id="99c61-111">attribute</span><span class="sxs-lookup"><span data-stu-id="99c61-111">Attribute</span></span>|<span data-ttu-id="99c61-112">Описание</span><span class="sxs-lookup"><span data-stu-id="99c61-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="99c61-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="99c61-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="99c61-114">Уточняется, создает <xref:System.Security.Policy.Publisher> ли время выполнения доказательства.</span><span class="sxs-lookup"><span data-stu-id="99c61-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="99c61-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="99c61-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="99c61-116">Значение</span><span class="sxs-lookup"><span data-stu-id="99c61-116">Value</span></span>|<span data-ttu-id="99c61-117">Описание</span><span class="sxs-lookup"><span data-stu-id="99c61-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="99c61-118">Не создает <xref:System.Security.Policy.Publisher> доказательств.</span><span class="sxs-lookup"><span data-stu-id="99c61-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="99c61-119">Создает <xref:System.Security.Policy.Publisher> доказательства.</span><span class="sxs-lookup"><span data-stu-id="99c61-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="99c61-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="99c61-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99c61-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="99c61-121">Child Elements</span></span>  
 <span data-ttu-id="99c61-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="99c61-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99c61-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="99c61-123">Parent Elements</span></span>  
  
|<span data-ttu-id="99c61-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="99c61-124">Element</span></span>|<span data-ttu-id="99c61-125">Описание</span><span class="sxs-lookup"><span data-stu-id="99c61-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="99c61-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="99c61-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="99c61-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="99c61-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99c61-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="99c61-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99c61-129">В рамках .NET 4 и позже этот элемент не влияет на время сборки.</span><span class="sxs-lookup"><span data-stu-id="99c61-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="99c61-130">Для получения дополнительной информации смотрите раздел "Упрощение политики [безопасности" в разделе "Изменения безопасности".](../../../security/security-changes.md)</span><span class="sxs-lookup"><span data-stu-id="99c61-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="99c61-131">Общее время выполнения языка (CLR) пытается проверить подпись Authenticode <xref:System.Security.Policy.Publisher> во время загрузки, чтобы создать улики для сборки.</span><span class="sxs-lookup"><span data-stu-id="99c61-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="99c61-132">Однако по умолчанию большинству <xref:System.Security.Policy.Publisher> приложений не нужны доказательства.</span><span class="sxs-lookup"><span data-stu-id="99c61-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="99c61-133">Стандартная политика CAS не <xref:System.Security.Policy.PublisherMembershipCondition>опирается на .</span><span class="sxs-lookup"><span data-stu-id="99c61-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="99c61-134">Следует избегать ненужных затрат на запуск, связанных с проверкой подписи издателя, если приложение не <xref:System.Security.Permissions.PublisherIdentityPermission> выполняется на компьютере с пользовательской политикой CAS или не намерено удовлетворять требования в среде частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="99c61-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="99c61-135">(Требования к разрешению на идентификацию всегда удались в условиях полного доверия.)</span><span class="sxs-lookup"><span data-stu-id="99c61-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99c61-136">Мы рекомендуем службам `<generatePublisherEvidence>` использовать элемент для повышения производительности запуска.</span><span class="sxs-lookup"><span data-stu-id="99c61-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="99c61-137">Использование этого элемента также может помочь избежать задержек, которые могут привести к тайм-ауту и отмене запуска службы.</span><span class="sxs-lookup"><span data-stu-id="99c61-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="99c61-138">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="99c61-138">Configuration File</span></span>  
 <span data-ttu-id="99c61-139">Этот элемент может быть использован только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="99c61-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99c61-140">Пример</span><span class="sxs-lookup"><span data-stu-id="99c61-140">Example</span></span>  
 <span data-ttu-id="99c61-141">Ниже приводится следующий `<generatePublisherEvidence>` пример, как использовать элемент для отсеивания проверки политики издателя CAS для приложения.</span><span class="sxs-lookup"><span data-stu-id="99c61-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99c61-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="99c61-142">See also</span></span>

- [<span data-ttu-id="99c61-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="99c61-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="99c61-144">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="99c61-144">Configuration File Schema</span></span>](../index.md)
