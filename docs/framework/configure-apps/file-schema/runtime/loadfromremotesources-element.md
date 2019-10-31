---
title: Элемент <loadFromRemoteSources>
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a4dbcd0a0b848e5ef57965b5b3f4fcee9161b724
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116568"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="97590-102">\<Лоадфромремотесаурцес > элемент</span><span class="sxs-lookup"><span data-stu-id="97590-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="97590-103">Указывает, должны ли сборки, загруженные из удаленных источников, предоставлять полное доверие в .NET Framework 4 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="97590-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="97590-104">Если вы перенаправлялись на эту статью из-за сообщения об ошибке в списке ошибок проекта Visual Studio или ошибки сборки, см. раздел [как использовать сборку из Интернета в Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="97590-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
<span data-ttu-id="97590-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="97590-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="97590-106">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="97590-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="97590-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<лоадфромремотесаурцес >**</span><span class="sxs-lookup"><span data-stu-id="97590-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97590-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97590-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97590-109">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="97590-109">Attributes and elements</span></span>
 <span data-ttu-id="97590-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="97590-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97590-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="97590-111">Attributes</span></span>  
  
|<span data-ttu-id="97590-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="97590-112">Attribute</span></span>|<span data-ttu-id="97590-113">Описание</span><span class="sxs-lookup"><span data-stu-id="97590-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="97590-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="97590-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="97590-115">Указывает, должно ли быть предоставлено полное доверие для сборки, загружаемой из удаленного источника.</span><span class="sxs-lookup"><span data-stu-id="97590-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="97590-116">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="97590-116">enabled attribute</span></span>  
  
|<span data-ttu-id="97590-117">значения</span><span class="sxs-lookup"><span data-stu-id="97590-117">Value</span></span>|<span data-ttu-id="97590-118">Описание</span><span class="sxs-lookup"><span data-stu-id="97590-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="97590-119">Не предоставляйте полное доверие приложениям из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="97590-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="97590-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="97590-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="97590-121">Предоставление полного доверия приложениям из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="97590-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97590-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="97590-122">Child elements</span></span>  
 <span data-ttu-id="97590-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="97590-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97590-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="97590-124">Parent elements</span></span>  
  
|<span data-ttu-id="97590-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="97590-125">Element</span></span>|<span data-ttu-id="97590-126">Описание</span><span class="sxs-lookup"><span data-stu-id="97590-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="97590-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97590-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="97590-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="97590-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97590-129">Заметки</span><span class="sxs-lookup"><span data-stu-id="97590-129">Remarks</span></span>

<span data-ttu-id="97590-130">В .NET Framework 3,5 и более ранних версиях при загрузке сборки из удаленного расположения код в сборке выполняется в режиме частичного доверия с набором разрешений, зависящим от зоны, из которой она загружена.</span><span class="sxs-lookup"><span data-stu-id="97590-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="97590-131">Например, если загрузить сборку с веб-сайта, она загружается в зону Интернета и предоставляет набор разрешений Интернета.</span><span class="sxs-lookup"><span data-stu-id="97590-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="97590-132">Иными словами, он выполняется в песочнице Интернета.</span><span class="sxs-lookup"><span data-stu-id="97590-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="97590-133">Начиная с .NET Framework 4, политика разграничения доступа кода (CAS) отключена, и сборки загружаются с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="97590-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="97590-134">Обычно это обеспечивает полное доверие сборкам, загруженным с помощью метода <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>, который ранее был изолирован.</span><span class="sxs-lookup"><span data-stu-id="97590-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="97590-135">Чтобы предотвратить это, возможность запуска кода в сборках, загружаемых из удаленного источника, по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="97590-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="97590-136">По умолчанию при попытке загрузить удаленную сборку выдается <xref:System.IO.FileLoadException> с сообщением об исключении следующего вида:</span><span class="sxs-lookup"><span data-stu-id="97590-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

<span data-ttu-id="97590-137">Для загрузки сборки и выполнения ее кода необходимо выполнить одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="97590-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="97590-138">Явно Создайте песочницу для сборки (см. раздел [как запустить частично доверенный код в песочнице](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="97590-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="97590-139">Запустите код сборки в режиме полного доверия.</span><span class="sxs-lookup"><span data-stu-id="97590-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="97590-140">Это можно сделать, настроив элемент `<loadFromRemoteSources>`.</span><span class="sxs-lookup"><span data-stu-id="97590-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="97590-141">Он позволяет указать, что сборки, выполняемые в режиме частичного доверия в более ранних версиях .NET Framework теперь выполняются с полным доверием в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="97590-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97590-142">Если сборка не должна выполняться с полным доверием, не устанавливайте этот элемент конфигурации.</span><span class="sxs-lookup"><span data-stu-id="97590-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="97590-143">Вместо этого создайте изолированную <xref:System.AppDomain>, в которую будет загружена сборка.</span><span class="sxs-lookup"><span data-stu-id="97590-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="97590-144">Атрибут `enabled` элемента `<loadFromRemoteSources>` эффективен, только если отключена разграничение доступа кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="97590-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="97590-145">По умолчанию политика CAS отключена в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="97590-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="97590-146">Если для `enabled` задано значение `true`, удаленным сборкам будет предоставлено полное доверие.</span><span class="sxs-lookup"><span data-stu-id="97590-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="97590-147">Если для `enabled` не задано значение `true`, <xref:System.IO.FileLoadException> создается при любом из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="97590-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="97590-148">Поведение "песочницы" текущего домена отличается от поведения в .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="97590-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="97590-149">Для этого требуется отключить политику разграничения доступа, а текущий домен не должен быть изолирован.</span><span class="sxs-lookup"><span data-stu-id="97590-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="97590-150">Загружаемая сборка не принадлежит зоне `MyComputer`.</span><span class="sxs-lookup"><span data-stu-id="97590-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="97590-151">Присвоение элементу `<loadFromRemoteSources>` значения `true` предотвращает возникновение этого исключения.</span><span class="sxs-lookup"><span data-stu-id="97590-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="97590-152">Он позволяет указать, что вы не полагаетесь на среду CLR для использования песочницы загруженными сборками для обеспечения безопасности и можете ли они быть разрешены для выполнения с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="97590-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="97590-153">Примечания</span><span class="sxs-lookup"><span data-stu-id="97590-153">Notes</span></span>

- <span data-ttu-id="97590-154">В .NET Framework 4,5 и более поздних версиях сборки на локальных сетевых ресурсах по умолчанию работают в режиме полного доверия. не нужно включать элемент `<loadFromRemoteSources>`.</span><span class="sxs-lookup"><span data-stu-id="97590-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="97590-155">Если приложение скопировано из Интернета, оно помечается ОС Windows как веб-приложение, даже если находится на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="97590-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="97590-156">Это обозначение можно изменить, изменив его свойства файла. также можно использовать элемент `<loadFromRemoteSources>`, чтобы предоставить сборке полное доверие.</span><span class="sxs-lookup"><span data-stu-id="97590-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="97590-157">Также можно использовать метод <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A>, чтобы загрузить локальную сборку, которую операционная система пометила как загруженную из Интернета.</span><span class="sxs-lookup"><span data-stu-id="97590-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="97590-158">Вы можете получить <xref:System.IO.FileLoadException> в приложении, которое выполняется в приложении Windows Virtual PC.</span><span class="sxs-lookup"><span data-stu-id="97590-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="97590-159">Это может произойти при попытке загрузить файл из связанных папок на компьютере размещения.</span><span class="sxs-lookup"><span data-stu-id="97590-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="97590-160">Это также может произойти при попытке загрузить файл из папки, связанной [службы удаленных рабочих столов](https://go.microsoft.com/fwlink/?LinkId=182775) (службы терминалов).</span><span class="sxs-lookup"><span data-stu-id="97590-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="97590-161">Чтобы избежать исключения, задайте для параметра `enabled` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="97590-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="97590-162">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="97590-162">Configuration file</span></span>

<span data-ttu-id="97590-163">Этот элемент обычно используется в файле конфигурации приложения, но может использоваться в других файлах конфигурации в зависимости от контекста.</span><span class="sxs-lookup"><span data-stu-id="97590-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="97590-164">Дополнительные сведения см. в статье [более Неявное использование политики CAS: лоадфромремотесаурцес](https://go.microsoft.com/fwlink/p/?LinkId=266839) в блоге по безопасности .NET.</span><span class="sxs-lookup"><span data-stu-id="97590-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="97590-165">Пример</span><span class="sxs-lookup"><span data-stu-id="97590-165">Example</span></span>

<span data-ttu-id="97590-166">В следующем примере показано, как предоставить полное доверие сборкам, загруженным из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="97590-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="97590-167">См. также</span><span class="sxs-lookup"><span data-stu-id="97590-167">See also</span></span>

- [<span data-ttu-id="97590-168">Более Неявное использование политики CAS: Лоадфромремотесаурцес</span><span class="sxs-lookup"><span data-stu-id="97590-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=266839)
- [<span data-ttu-id="97590-169">Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде</span><span class="sxs-lookup"><span data-stu-id="97590-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="97590-170">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="97590-170">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="97590-171">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="97590-171">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
