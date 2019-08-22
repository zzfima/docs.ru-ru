---
title: Элемент <NetFx40_LegacySecurityPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 881862b6b81ace1c1923b2a22d2fbe54d939d84e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663560"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="e7af0-102">\<Элемент > NetFx40_LegacySecurityPolicy</span><span class="sxs-lookup"><span data-stu-id="e7af0-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="e7af0-103">Указывает, использует ли среда выполнения устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="e7af0-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

<span data-ttu-id="e7af0-104">\<> конфигурации </span><span class="sxs-lookup"><span data-stu-id="e7af0-104">\<configuration></span></span>\
<span data-ttu-id="e7af0-105">\<> среды выполнения </span><span class="sxs-lookup"><span data-stu-id="e7af0-105">\<runtime></span></span>\
<span data-ttu-id="e7af0-106">\<NetFx40_LegacySecurityPolicy ></span><span class="sxs-lookup"><span data-stu-id="e7af0-106">\<NetFx40_LegacySecurityPolicy></span></span>

## <a name="syntax"></a><span data-ttu-id="e7af0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7af0-107">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e7af0-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e7af0-108">Attributes and Elements</span></span>

<span data-ttu-id="e7af0-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e7af0-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e7af0-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7af0-110">Attributes</span></span>

|<span data-ttu-id="e7af0-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e7af0-111">Attribute</span></span>|<span data-ttu-id="e7af0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e7af0-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="e7af0-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e7af0-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e7af0-114">Указывает, использует ли среда выполнения устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="e7af0-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="e7af0-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="e7af0-115">enabled Attribute</span></span>

|<span data-ttu-id="e7af0-116">Значение</span><span class="sxs-lookup"><span data-stu-id="e7af0-116">Value</span></span>|<span data-ttu-id="e7af0-117">Описание</span><span class="sxs-lookup"><span data-stu-id="e7af0-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="e7af0-118">Среда выполнения не использует устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="e7af0-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="e7af0-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e7af0-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="e7af0-120">Среда выполнения использует устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="e7af0-120">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e7af0-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7af0-121">Child Elements</span></span>

<span data-ttu-id="e7af0-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="e7af0-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e7af0-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e7af0-123">Parent Elements</span></span>

|<span data-ttu-id="e7af0-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7af0-124">Element</span></span>|<span data-ttu-id="e7af0-125">Описание</span><span class="sxs-lookup"><span data-stu-id="e7af0-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="e7af0-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7af0-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="e7af0-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e7af0-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e7af0-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7af0-128">Remarks</span></span>

<span data-ttu-id="e7af0-129">В .NET Framework версии 3,5 и более ранних версиях политика CAS действует всегда.</span><span class="sxs-lookup"><span data-stu-id="e7af0-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="e7af0-130">В .NET Framework 4 политика CAS должна быть включена.</span><span class="sxs-lookup"><span data-stu-id="e7af0-130">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="e7af0-131">Политика CAS зависит от версии.</span><span class="sxs-lookup"><span data-stu-id="e7af0-131">CAS policy is version-specific.</span></span> <span data-ttu-id="e7af0-132">Пользовательские политики CAS, существующие в более ранних версиях .NET Framework, должны быть указаны в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e7af0-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="e7af0-133">Применение элемента к сборке .NET Framework 4 не влияет на прозрачный для [безопасности код](../../../misc/security-transparent-code.md); правила прозрачности по-прежнему применяются. `<NetFx40_LegacySecurityPolicy>`</span><span class="sxs-lookup"><span data-stu-id="e7af0-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7af0-134">Применение элемента может привести к значительному снижению производительности для сборок образов в машинном кодах, созданных [генератором образов в машинном кодах (Ngen. exe)](../../../tools/ngen-exe-native-image-generator.md) , которые не установлены в [глобальном кэше сборок.](../../../app-domains/gac.md) `<NetFx40_LegacySecurityPolicy>`</span><span class="sxs-lookup"><span data-stu-id="e7af0-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="e7af0-135">Снижение производительности вызвано невозможностью загрузки средой выполнения сборок в качестве образов в машинном код при применении атрибута, что приводит к их загрузке как JIT-сборки.</span><span class="sxs-lookup"><span data-stu-id="e7af0-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="e7af0-136">Если указать целевую версию .NET Framework более раннюю, чем .NET Framework 4 в параметрах проекта для проекта Visual Studio, будет включена политика CAS, включая любые пользовательские политики CAS, указанные для этой версии.</span><span class="sxs-lookup"><span data-stu-id="e7af0-136">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="e7af0-137">Однако вы не сможете использовать новые типы и члены .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e7af0-137">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="e7af0-138">Кроме того, можно указать более раннюю версию .NET Framework с помощью [ \<элемента > supportedRuntime](../startup/supportedruntime-element.md) в схеме параметров запуска в [файле конфигурации приложения](../../index.md).</span><span class="sxs-lookup"><span data-stu-id="e7af0-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e7af0-139">В синтаксисе файла конфигурации учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="e7af0-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="e7af0-140">Следует использовать синтаксис, указанный в разделах синтаксис и пример.</span><span class="sxs-lookup"><span data-stu-id="e7af0-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="e7af0-141">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="e7af0-141">Configuration File</span></span>

<span data-ttu-id="e7af0-142">Этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e7af0-142">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="e7af0-143">Пример</span><span class="sxs-lookup"><span data-stu-id="e7af0-143">Example</span></span>

<span data-ttu-id="e7af0-144">В следующем примере показано, как включить устаревшую политику CAS для приложения.</span><span class="sxs-lookup"><span data-stu-id="e7af0-144">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e7af0-145">См. также</span><span class="sxs-lookup"><span data-stu-id="e7af0-145">See also</span></span>

- [<span data-ttu-id="e7af0-146">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e7af0-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e7af0-147">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e7af0-147">Configuration File Schema</span></span>](../index.md)
