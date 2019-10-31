---
title: Элемент <NetFx40_LegacySecurityPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
ms.openlocfilehash: d5192eb56bb8b640544bdc52a0bb9d8a5277efef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116251"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="b6b9f-102">\<NetFx40_LegacySecurityPolicy > элемент</span><span class="sxs-lookup"><span data-stu-id="b6b9f-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="b6b9f-103">Указывает, использует ли среда выполнения устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

<span data-ttu-id="b6b9f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6b9f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6b9f-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="b6b9f-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="b6b9f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<NetFx40_LegacySecurityPolicy >**</span><span class="sxs-lookup"><span data-stu-id="b6b9f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_LegacySecurityPolicy>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="b6b9f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6b9f-107">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b6b9f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6b9f-108">Attributes and Elements</span></span>

<span data-ttu-id="b6b9f-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b6b9f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6b9f-110">Attributes</span></span>

|<span data-ttu-id="b6b9f-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b6b9f-111">Attribute</span></span>|<span data-ttu-id="b6b9f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b6b9f-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="b6b9f-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b6b9f-114">Указывает, использует ли среда выполнения устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="b6b9f-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="b6b9f-115">enabled Attribute</span></span>

|<span data-ttu-id="b6b9f-116">значения</span><span class="sxs-lookup"><span data-stu-id="b6b9f-116">Value</span></span>|<span data-ttu-id="b6b9f-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b6b9f-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="b6b9f-118">Среда выполнения не использует устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="b6b9f-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="b6b9f-120">Среда выполнения использует устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-120">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b6b9f-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6b9f-121">Child Elements</span></span>

<span data-ttu-id="b6b9f-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b6b9f-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6b9f-123">Parent Elements</span></span>

|<span data-ttu-id="b6b9f-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6b9f-124">Element</span></span>|<span data-ttu-id="b6b9f-125">Описание</span><span class="sxs-lookup"><span data-stu-id="b6b9f-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="b6b9f-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="b6b9f-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b6b9f-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="b6b9f-128">Remarks</span></span>

<span data-ttu-id="b6b9f-129">В .NET Framework версии 3,5 и более ранних версиях политика CAS действует всегда.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="b6b9f-130">В .NET Framework 4 политика CAS должна быть включена.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-130">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="b6b9f-131">Политика CAS зависит от версии.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-131">CAS policy is version-specific.</span></span> <span data-ttu-id="b6b9f-132">Пользовательские политики CAS, существующие в более ранних версиях .NET Framework, должны быть указаны в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="b6b9f-133">Применение элемента `<NetFx40_LegacySecurityPolicy>` к сборке .NET Framework 4 не влияет на код, [прозрачный для безопасности](../../../misc/security-transparent-code.md); правила прозрачности по-прежнему применяются.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6b9f-134">Применение элемента `<NetFx40_LegacySecurityPolicy>` может привести к значительному снижению производительности сборок образов в машинном кодах, созданных [генератором образов в машинном кодах (Ngen. exe)](../../../tools/ngen-exe-native-image-generator.md) , которые не установлены в [глобальном кэше сборок](../../../app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="b6b9f-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="b6b9f-135">Снижение производительности вызвано невозможностью загрузки средой выполнения сборок в качестве образов в машинном код при применении атрибута, что приводит к их загрузке как JIT-сборки.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="b6b9f-136">Если указать целевую версию .NET Framework более раннюю, чем .NET Framework 4 в параметрах проекта для проекта Visual Studio, будет включена политика CAS, включая любые пользовательские политики CAS, указанные для этой версии.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-136">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="b6b9f-137">Однако вы не сможете использовать новые типы и члены .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-137">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="b6b9f-138">Вы также можете указать более раннюю версию .NET Framework с помощью [элемента\<supportedRuntime >](../startup/supportedruntime-element.md) в схеме параметров запуска в [файле конфигурации приложения](../../index.md).</span><span class="sxs-lookup"><span data-stu-id="b6b9f-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b6b9f-139">В синтаксисе файла конфигурации учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="b6b9f-140">Следует использовать синтаксис, указанный в разделах синтаксис и пример.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="b6b9f-141">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="b6b9f-141">Configuration File</span></span>

<span data-ttu-id="b6b9f-142">Этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-142">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="b6b9f-143">Пример</span><span class="sxs-lookup"><span data-stu-id="b6b9f-143">Example</span></span>

<span data-ttu-id="b6b9f-144">В следующем примере показано, как включить устаревшую политику CAS для приложения.</span><span class="sxs-lookup"><span data-stu-id="b6b9f-144">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b6b9f-145">См. также</span><span class="sxs-lookup"><span data-stu-id="b6b9f-145">See also</span></span>

- [<span data-ttu-id="b6b9f-146">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="b6b9f-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b6b9f-147">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="b6b9f-147">Configuration File Schema</span></span>](../index.md)
