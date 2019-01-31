---
title: Элемент <loadFromRemoteSources>
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ebb32a74f5413f9c927a84ababf2d60d20e0b024
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269696"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="1a085-102">\<loadFromRemoteSources > элемент</span><span class="sxs-lookup"><span data-stu-id="1a085-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="1a085-103">Указывает, следует ли предоставлять полное доверие в .NET Framework 4 и более поздних версий сборки, загруженные из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="1a085-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="1a085-104">Если вы перешли на этот раздел из-за сообщение об ошибке в списке ошибок Visual Studio проекта или ошибка сборки, см. в разделе [как: Использовать сборку из Интернета в Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span><span class="sxs-lookup"><span data-stu-id="1a085-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="1a085-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1a085-105">\<configuration></span></span>  
<span data-ttu-id="1a085-106">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="1a085-106">\<runtime></span></span>  
<span data-ttu-id="1a085-107">\<loadFromRemoteSources ></span><span class="sxs-lookup"><span data-stu-id="1a085-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a085-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a085-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a085-109">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="1a085-109">Attributes and elements</span></span>
 <span data-ttu-id="1a085-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1a085-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a085-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1a085-111">Attributes</span></span>  
  
|<span data-ttu-id="1a085-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1a085-112">Attribute</span></span>|<span data-ttu-id="1a085-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1a085-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1a085-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="1a085-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="1a085-115">Указывает, следует ли предоставлять полного уровня доверия сборки, загруженной из удаленного источника.</span><span class="sxs-lookup"><span data-stu-id="1a085-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1a085-116">атрибут Enabled</span><span class="sxs-lookup"><span data-stu-id="1a085-116">enabled attribute</span></span>  
  
|<span data-ttu-id="1a085-117">Значение</span><span class="sxs-lookup"><span data-stu-id="1a085-117">Value</span></span>|<span data-ttu-id="1a085-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="1a085-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1a085-119">Не предоставляйте полное доверие к приложениям из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="1a085-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="1a085-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1a085-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="1a085-121">Предоставить полное доверие к приложениям из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="1a085-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a085-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1a085-122">Child elements</span></span>  
 <span data-ttu-id="1a085-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1a085-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a085-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1a085-124">Parent elements</span></span>  
  
|<span data-ttu-id="1a085-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="1a085-125">Element</span></span>|<span data-ttu-id="1a085-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="1a085-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1a085-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1a085-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1a085-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="1a085-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a085-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a085-129">Remarks</span></span>

<span data-ttu-id="1a085-130">В .NET Framework 3.5 и более ранних версий Если загрузить сборку из удаленного расположения, код в сборке, выполняется в режиме частичного доверия с набором прав, который зависит от зоны, из которого загружается.</span><span class="sxs-lookup"><span data-stu-id="1a085-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="1a085-131">Например если сборку загрузить с веб-сайта, он загружается в зоне Интернета и предоставлен набор разрешений Интернета.</span><span class="sxs-lookup"><span data-stu-id="1a085-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="1a085-132">Другими словами он выполняет в песочнице Интернета.</span><span class="sxs-lookup"><span data-stu-id="1a085-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="1a085-133">Начиная с .NET Framework 4, политику разграничения доступа кода отключена и сборки загружаются в режиме полного доверия.</span><span class="sxs-lookup"><span data-stu-id="1a085-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="1a085-134">Как правило, это предоставить полное доверие для сборки, загруженные с <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> метод, который ранее был изолированной.</span><span class="sxs-lookup"><span data-stu-id="1a085-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="1a085-135">Чтобы избежать этого, по умолчанию отключена возможность запуска кода в сборки, загруженные из удаленного источника.</span><span class="sxs-lookup"><span data-stu-id="1a085-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="1a085-136">По умолчанию, при попытке загрузить удаленную сборку <xref:System.IO.FileLoadException> с сообщением об исключении, как возникает следующее:</span><span class="sxs-lookup"><span data-stu-id="1a085-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

<span data-ttu-id="1a085-137">Для загрузки сборки и выполнения его кода, необходимо:</span><span class="sxs-lookup"><span data-stu-id="1a085-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="1a085-138">Явным образом создать "песочницу" для сборки (см. в разделе [как: Запустите частично доверенного кода в изолированной среде](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="1a085-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="1a085-139">Выполнение кода сборки с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="1a085-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="1a085-140">Это можно сделать, настроив `<loadFromRemoteSources>` элемент.</span><span class="sxs-lookup"><span data-stu-id="1a085-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="1a085-141">Он позволяет указать, что сборки, работающих в режиме частичного доверия в более ранних версиях платформы .NET Framework теперь выполняются в режиме полного доверия в .NET Framework 4 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="1a085-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a085-142">Если сборки не должно выполняться в режиме полного доверия, не устанавливайте этот элемент конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1a085-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="1a085-143">Вместо этого создайте изолированной <xref:System.AppDomain> для загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="1a085-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="1a085-144">`enabled` Для атрибута `<loadFromRemoteSources>` элемент действует, только когда отключено управление доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="1a085-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="1a085-145">По умолчанию политика CAS отключена в .NET Framework 4 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="1a085-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="1a085-146">Если задать `enabled` для `true`, удаленного сборкам предоставляется полное доверие.</span><span class="sxs-lookup"><span data-stu-id="1a085-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="1a085-147">Если `enabled` равно `true`, <xref:System.IO.FileLoadException> возникает исключение в одном из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="1a085-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="1a085-148">Поведение "песочницы" текущего домена отличается от его поведение в .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="1a085-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="1a085-149">Для этого политики разграничения доступа кода отключена и текущий домен не изолирована.</span><span class="sxs-lookup"><span data-stu-id="1a085-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="1a085-150">Загружаемая сборка не из `MyComputer` зоны.</span><span class="sxs-lookup"><span data-stu-id="1a085-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="1a085-151">Установка `<loadFromRemoteSources>` элемент `true` предотвращает это исключение вызывается.</span><span class="sxs-lookup"><span data-stu-id="1a085-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="1a085-152">Он позволяет указать, что вы не полагаетесь на среда CLR для "песочницы" загруженных сборок в, и что они могут быть могут выполняться в режиме полного доверия.</span><span class="sxs-lookup"><span data-stu-id="1a085-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="1a085-153">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a085-153">Notes</span></span>

- <span data-ttu-id="1a085-154">В .NET Framework 4.5 и более поздних версий сборки в общих папках локальной сети выполняются в режиме полного доверия по умолчанию. необходимо включить `<loadFromRemoteSources>` элемент.</span><span class="sxs-lookup"><span data-stu-id="1a085-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="1a085-155">Если приложение скопировано из Интернета, оно помечается ОС Windows как веб-приложение, даже если находится на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1a085-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="1a085-156">Это обозначение можно изменить, изменив его свойства файла, или воспользоваться `<loadFromRemoteSources>` элемент для предоставления сборке полное доверие.</span><span class="sxs-lookup"><span data-stu-id="1a085-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="1a085-157">Также можно использовать метод <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A>, чтобы загрузить локальную сборку, которую операционная система пометила как загруженную из Интернета.</span><span class="sxs-lookup"><span data-stu-id="1a085-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="1a085-158">Может появиться <xref:System.IO.FileLoadException> в приложении, которое выполняется в приложении Windows Virtual PC.</span><span class="sxs-lookup"><span data-stu-id="1a085-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="1a085-159">Это может произойти при попытке загрузить файл из связанных папок на компьютера для размещения.</span><span class="sxs-lookup"><span data-stu-id="1a085-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="1a085-160">Она также может возникать при попытке загрузить файл из папки, связанной через [служб удаленных рабочих столов](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services Client).</span><span class="sxs-lookup"><span data-stu-id="1a085-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="1a085-161">Чтобы избежать этого исключения, задайте `enabled` для `true`.</span><span class="sxs-lookup"><span data-stu-id="1a085-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="1a085-162">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="1a085-162">Configuration file</span></span>

<span data-ttu-id="1a085-163">Этот элемент обычно используется в файле конфигурации приложения, но может использоваться в других файлах конфигурации в зависимости от контекста.</span><span class="sxs-lookup"><span data-stu-id="1a085-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="1a085-164">Дополнительные сведения см. в статье [дополнительные неявного использования политики CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) в блоге .NET Security.</span><span class="sxs-lookup"><span data-stu-id="1a085-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="1a085-165">Пример</span><span class="sxs-lookup"><span data-stu-id="1a085-165">Example</span></span>

<span data-ttu-id="1a085-166">В следующем примере показано, как предоставить полное доверие для сборок, загруженных из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="1a085-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="1a085-167">См. также</span><span class="sxs-lookup"><span data-stu-id="1a085-167">See also</span></span>

- [<span data-ttu-id="1a085-168">Более неявного использования политики CAS: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="1a085-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=266839)
- [<span data-ttu-id="1a085-169">Практическое руководство. Выполнение частично доверенного кода в изолированной среде</span><span class="sxs-lookup"><span data-stu-id="1a085-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="1a085-170">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="1a085-170">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="1a085-171">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="1a085-171">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
