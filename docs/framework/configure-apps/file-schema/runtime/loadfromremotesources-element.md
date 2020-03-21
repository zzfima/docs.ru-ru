---
title: Элемент <loadFromRemoteSources>
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154066"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="bc0fd-102">\<loadFromRemoteSources> элемент</span><span class="sxs-lookup"><span data-stu-id="bc0fd-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="bc0fd-103">Уточняется, следует ли предоставить сборки, загруженные из удаленных источников, полное доверие к .NET Framework 4 и позже.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bc0fd-104">Если вы были направлены на эту статью из-за сообщения об ошибке в списке ошибок проекта Visual Studio или ошибки сборки, [см.](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bc0fd-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
<span data-ttu-id="bc0fd-105">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bc0fd-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bc0fd-106">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="bc0fd-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="bc0fd-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteИсточники>**</span><span class="sxs-lookup"><span data-stu-id="bc0fd-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc0fd-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc0fd-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc0fd-109">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="bc0fd-109">Attributes and elements</span></span>
 <span data-ttu-id="bc0fd-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc0fd-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bc0fd-111">Attributes</span></span>  
  
|<span data-ttu-id="bc0fd-112">attribute</span><span class="sxs-lookup"><span data-stu-id="bc0fd-112">Attribute</span></span>|<span data-ttu-id="bc0fd-113">Описание</span><span class="sxs-lookup"><span data-stu-id="bc0fd-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="bc0fd-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="bc0fd-115">Уточняется, следует ли получить полное доверие сборке, загруженной из удаленного источника.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bc0fd-116">включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="bc0fd-116">enabled attribute</span></span>  
  
|<span data-ttu-id="bc0fd-117">Значение</span><span class="sxs-lookup"><span data-stu-id="bc0fd-117">Value</span></span>|<span data-ttu-id="bc0fd-118">Описание</span><span class="sxs-lookup"><span data-stu-id="bc0fd-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="bc0fd-119">Не доверяйте приложениям из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="bc0fd-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="bc0fd-121">Предоставляете полное доверие приложениям из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc0fd-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bc0fd-122">Child elements</span></span>  
 <span data-ttu-id="bc0fd-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bc0fd-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bc0fd-124">Parent elements</span></span>  
  
|<span data-ttu-id="bc0fd-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="bc0fd-125">Element</span></span>|<span data-ttu-id="bc0fd-126">Описание</span><span class="sxs-lookup"><span data-stu-id="bc0fd-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bc0fd-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bc0fd-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc0fd-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="bc0fd-129">Remarks</span></span>

<span data-ttu-id="bc0fd-130">В системе .NET 3.5 и более ранних версиях при загрузке сборки из удаленного местоположения код в сборке выполняется в частичном доверии с набором грантов, который зависит от зоны, из которой он загружается.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="bc0fd-131">Например, если вы загружаете сборку с веб-сайта, она загружается в интернет-зону и предоставляется набор разрешений в Интернете.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="bc0fd-132">Другими словами, он выполняет в интернет-песочнице.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="bc0fd-133">Начиная с .NET Framework 4, политика безопасности доступа к кодам (CAS) отключена, а сборки загружаются в полном доверии.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="bc0fd-134">Обычно это дает полное доверие к сборкам, загруженным <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> методом, который ранее был песочницей.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="bc0fd-135">Чтобы предотвратить это, возможность запуска кода в сборках, загруженных из удаленного источника, отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="bc0fd-136">По умолчанию при попытке загрузки <xref:System.IO.FileLoadException> удаленной сборки выбрасывается сообщение с исключением, подобное следующему:</span><span class="sxs-lookup"><span data-stu-id="bc0fd-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

<span data-ttu-id="bc0fd-137">Чтобы загрузить сборку и выполнить ее код, необходимо:</span><span class="sxs-lookup"><span data-stu-id="bc0fd-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="bc0fd-138">Явно создайте песочницу для сборки (см. [Как: Выполнить частично доверенный код в песочнице).](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)</span><span class="sxs-lookup"><span data-stu-id="bc0fd-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="bc0fd-139">Запустите код сборки в полном доверии.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="bc0fd-140">Вы делаете это путем `<loadFromRemoteSources>` настройки элемента.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="bc0fd-141">Это позволяет указать, что сборки, которые работают в частичном доверии к более ранним версиям рамочного соглашения .NET, теперь работают в полном доверии к .NET Framework 4 и более поздним версиям.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc0fd-142">Если сборка не должна выполняться в полном доверии, не устанавливайте этот элемент конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="bc0fd-143">Вместо этого создайте песочницу, <xref:System.AppDomain> в которой можно загрузить сборку.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="bc0fd-144">Атрибут `enabled` элемента `<loadFromRemoteSources>` эффективен только при отключении безопасности доступа к коду (CAS).</span><span class="sxs-lookup"><span data-stu-id="bc0fd-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="bc0fd-145">По умолчанию политика CAS отключена в системе .NET 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="bc0fd-146">Если вы `enabled` `true`установите, удаленные сборки получают полное доверие.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="bc0fd-147">Если `enabled` не `true`установлен, <xref:System.IO.FileLoadException> то брошено под любым из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="bc0fd-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="bc0fd-148">Поведение текущего домена в песочнице отличается от его поведения в рамках .NET 3.5.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="bc0fd-149">Это требует, чтобы политика CAS была отключена, а текущий домен не был застечен на песочнице.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="bc0fd-150">Загрузка сборки не из `MyComputer` зоны.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="bc0fd-151">Настройка `<loadFromRemoteSources>` элемента для `true` предотвращения этого исключения от броски.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="bc0fd-152">Это позволяет указать, что вы не полагаетесь на общее время выполнения языка в песочнице загруженных сборок для обеспечения безопасности, и что они могут быть разрешены для выполнения в полном доверии.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="bc0fd-153">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc0fd-153">Notes</span></span>

- <span data-ttu-id="bc0fd-154">В рамках .NET 4.5 и более поздних версиях сборки на локальных сетевых акциях работают в полном доверии по умолчанию; вы не должны включить `<loadFromRemoteSources>` элемент.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="bc0fd-155">Если приложение скопировано из Интернета, оно помечается ОС Windows как веб-приложение, даже если находится на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="bc0fd-156">Это обозначение можно изменить, изменив свойства файлов, или использовать `<loadFromRemoteSources>` элемент для предоставления сборке полного доверия.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="bc0fd-157">Также можно использовать метод <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A>, чтобы загрузить локальную сборку, которую операционная система пометила как загруженную из Интернета.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="bc0fd-158">Вы можете <xref:System.IO.FileLoadException> получить в приложении, которое работает в приложении Windows Virtual PC.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="bc0fd-159">Это может произойти при попытке загрузить файл из связанных папок на хостинг-компьютере.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="bc0fd-160">Это также может произойти при попытке загрузить файл из папки, связанной с [удаленными службами рабочего стола](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span><span class="sxs-lookup"><span data-stu-id="bc0fd-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="bc0fd-161">Чтобы избежать исключения, `enabled` `true`установите на .</span><span class="sxs-lookup"><span data-stu-id="bc0fd-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="bc0fd-162">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="bc0fd-162">Configuration file</span></span>

<span data-ttu-id="bc0fd-163">Этот элемент обычно используется в файле конфигурации приложения, но может использоваться в других файлах конфигурации в зависимости от контекста.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="bc0fd-164">Для получения дополнительной информации смотрите статью [Подробнее о неявных использованиях политики CAS: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) в блоге .NET Security.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="bc0fd-165">Пример</span><span class="sxs-lookup"><span data-stu-id="bc0fd-165">Example</span></span>

<span data-ttu-id="bc0fd-166">Ниже приводится следующий пример, как предоставить полное доверие к сборкам, загруженным из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="bc0fd-167">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bc0fd-167">See also</span></span>

- [<span data-ttu-id="bc0fd-168">Более неявное использование политики CAS: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="bc0fd-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="bc0fd-169">Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде</span><span class="sxs-lookup"><span data-stu-id="bc0fd-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="bc0fd-170">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="bc0fd-170">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bc0fd-171">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="bc0fd-171">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
