---
title: Элемент <bypassTrustedAppStrongNames>
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
ms.openlocfilehash: 50e67e97d74b896a680cc18270d32aa7a8eb8035
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118176"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="66f3a-102">Элемент \<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="66f3a-102">\<bypassTrustedAppStrongNames> Element</span></span>

<span data-ttu-id="66f3a-103">Указывает, следует ли обходить проверку строгих имен в сборках с полным доверием, загружаемых в <xref:System.AppDomain>с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="66f3a-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>

<span data-ttu-id="66f3a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="66f3a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="66f3a-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="66f3a-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="66f3a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<элемент bypasstrustedappstrongnames >**</span><span class="sxs-lookup"><span data-stu-id="66f3a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**</span></span>

## <a name="syntax"></a><span data-ttu-id="66f3a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66f3a-107">Syntax</span></span>

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="66f3a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="66f3a-108">Attributes and Elements</span></span>

<span data-ttu-id="66f3a-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="66f3a-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="66f3a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="66f3a-110">Attributes</span></span>

|<span data-ttu-id="66f3a-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="66f3a-111">Attribute</span></span>|<span data-ttu-id="66f3a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="66f3a-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="66f3a-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="66f3a-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="66f3a-114">Указывает, включена ли функция обхода, которая не позволяет проверять строгие имена для сборок с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="66f3a-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="66f3a-115">Если эта функция включена, строгие имена не проверяются на правильность при загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="66f3a-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="66f3a-116">Значение по умолчанию: `true`.</span><span class="sxs-lookup"><span data-stu-id="66f3a-116">The default is `true`.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="66f3a-117">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="66f3a-117">enabled Attribute</span></span>

|<span data-ttu-id="66f3a-118">значения</span><span class="sxs-lookup"><span data-stu-id="66f3a-118">Value</span></span>|<span data-ttu-id="66f3a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="66f3a-119">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="66f3a-120">Подписи строгого имени в сборках с полным доверием не проверяются при загрузке сборок в <xref:System.AppDomain>с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="66f3a-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="66f3a-121">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="66f3a-121">This is the default.</span></span>|
|`false`|<span data-ttu-id="66f3a-122">Подписи строгого имени в сборках с полным доверием проверяются при загрузке сборок в <xref:System.AppDomain>с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="66f3a-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="66f3a-123">Подпись строгого имени проверяется только на правильность сигнатуры; оно не сравнивается с другим строгим именем для соответствия.</span><span class="sxs-lookup"><span data-stu-id="66f3a-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="66f3a-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="66f3a-124">Child Elements</span></span>

<span data-ttu-id="66f3a-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="66f3a-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="66f3a-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="66f3a-126">Parent Elements</span></span>

|<span data-ttu-id="66f3a-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="66f3a-127">Element</span></span>|<span data-ttu-id="66f3a-128">Описание</span><span class="sxs-lookup"><span data-stu-id="66f3a-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="66f3a-129">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="66f3a-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="66f3a-130">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="66f3a-130">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="66f3a-131">Заметки</span><span class="sxs-lookup"><span data-stu-id="66f3a-131">Remarks</span></span>

<span data-ttu-id="66f3a-132">Функция пропуска строгих имен позволяет избежать дополнительных затрат на проверку подписи строгого имени сборок с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="66f3a-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>

<span data-ttu-id="66f3a-133">Функция обхода применима к любой сборке, подписанной со строгим именем и имеющей следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="66f3a-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>

- <span data-ttu-id="66f3a-134">Полное доверие без <xref:System.Security.Policy.StrongName> свидетельства (например, имеет `MyComputer` свидетельство зоны).</span><span class="sxs-lookup"><span data-stu-id="66f3a-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>

- <span data-ttu-id="66f3a-135">Загрузка в домен <xref:System.AppDomain> с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="66f3a-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="66f3a-136">Загрузка из расположения со свойством <xref:System.AppDomainSetup.ApplicationBase%2A> домена <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="66f3a-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="66f3a-137">Подпись осуществлена без задержки.</span><span class="sxs-lookup"><span data-stu-id="66f3a-137">Not delay-signed.</span></span>

> [!NOTE]
> <span data-ttu-id="66f3a-138">Если функция обхода отключена для всех приложений на компьютере с помощью раздела реестра, этот параметр файла конфигурации не действует.</span><span class="sxs-lookup"><span data-stu-id="66f3a-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="66f3a-139">Дополнительные сведения см. в разделе [инструкции. Отключение функции обхода строгих имен](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="66f3a-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>

## <a name="example"></a><span data-ttu-id="66f3a-140">Пример</span><span class="sxs-lookup"><span data-stu-id="66f3a-140">Example</span></span>

<span data-ttu-id="66f3a-141">В следующем примере показано, как задать поведение, которое проверяет подпись строгого имени в сборках с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="66f3a-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="66f3a-142">См. также</span><span class="sxs-lookup"><span data-stu-id="66f3a-142">See also</span></span>

- [<span data-ttu-id="66f3a-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="66f3a-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="66f3a-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="66f3a-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="66f3a-145">Как отключить функцию обхода строгих имен</span><span class="sxs-lookup"><span data-stu-id="66f3a-145">How to: Disable the strong-name bypass feature</span></span>](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
