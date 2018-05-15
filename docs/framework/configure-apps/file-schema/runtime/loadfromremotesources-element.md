---
title: '&lt;loadFromRemoteSources&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0d442f71a0e2fc7deacd9aaa02cfba7b66f2349
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltloadfromremotesourcesgt-element"></a><span data-ttu-id="2c1e5-102">&lt;loadFromRemoteSources&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="2c1e5-102">&lt;loadFromRemoteSources&gt; Element</span></span>
<span data-ttu-id="2c1e5-103">Указывает, следует ли предоставлять полный уровень доверия сборки из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-103">Specifies whether assemblies from remote sources should be granted full trust.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c1e5-104">Если вы перешли на этот раздел из-за сообщения об ошибке в списке ошибок проекта Visual Studio или ошибку построения, в разделе [как: использовать сборку из Интернета в Visual Studio](http://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span><span class="sxs-lookup"><span data-stu-id="2c1e5-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](http://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="2c1e5-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2c1e5-105">\<configuration></span></span>  
<span data-ttu-id="2c1e5-106">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="2c1e5-106">\<runtime></span></span>  
<span data-ttu-id="2c1e5-107">\<loadFromRemoteSources ></span><span class="sxs-lookup"><span data-stu-id="2c1e5-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c1e5-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c1e5-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c1e5-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2c1e5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2c1e5-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c1e5-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2c1e5-111">Attributes</span></span>  
  
|<span data-ttu-id="2c1e5-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2c1e5-112">Attribute</span></span>|<span data-ttu-id="2c1e5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2c1e5-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="2c1e5-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="2c1e5-115">Указывает, следует ли предоставлять полный уровень доверия сборки, загруженной из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-115">Specifies whether an assembly that is loaded from remote sources should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2c1e5-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="2c1e5-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="2c1e5-117">Значение</span><span class="sxs-lookup"><span data-stu-id="2c1e5-117">Value</span></span>|<span data-ttu-id="2c1e5-118">Описание</span><span class="sxs-lookup"><span data-stu-id="2c1e5-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2c1e5-119">Не предоставляйте полное доверие приложениям из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="2c1e5-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="2c1e5-121">Предоставить полное доверие приложениям из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c1e5-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2c1e5-122">Child Elements</span></span>  
 <span data-ttu-id="2c1e5-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2c1e5-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2c1e5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2c1e5-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="2c1e5-125">Element</span></span>|<span data-ttu-id="2c1e5-126">Описание</span><span class="sxs-lookup"><span data-stu-id="2c1e5-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2c1e5-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2c1e5-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c1e5-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="2c1e5-129">Remarks</span></span>  
 <span data-ttu-id="2c1e5-130">В .NET Framework версии 3.5 и более ранних версий Если сборка загружена из удаленного расположения сборки будет выполняться частичным доверием с набором прав, который зависит от зоны, в которой она была загружена.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-130">In the .NET Framework version 3.5 and earlier versions, if you loaded an assembly from a remote location, the assembly would run partially trusted with a grant set that depended on the zone in which it was loaded.</span></span> <span data-ttu-id="2c1e5-131">Например, если вы загрузили сборку с веб-сайта, она была загружена в зону Интернета и получила набор разрешений Интернета.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-131">For example, if you loaded an assembly from a website, it was loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="2c1e5-132">Другими словами она выполнялась в изолированной Интернета.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-132">In other words, it executed in an Internet sandbox.</span></span> <span data-ttu-id="2c1e5-133">При попытке запустить эту сборку в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] и более поздних версиях возникает исключение, необходимо либо явным образом создать "песочницу" для сборки (см. [как: выполнение частично доверенного кода в изолированной среде](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), или выполнить его с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-133">If you try to run that assembly in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later versions, an exception is thrown; you must either explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), or run it in full trust.</span></span>  
  
 <span data-ttu-id="2c1e5-134">Элемент `<loadFromRemoteSources>` позволяет указать, что сборки, выполнявшиеся с частичным доверием в предыдущих версиях платформы .NET Framework, в платформе [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] и более поздних версиях следует выполнять с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-134">The `<loadFromRemoteSources>` element lets you specify that the assemblies that would have run partially trusted in earlier versions of the .NET Framework are to be run fully trusted in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later versions.</span></span> <span data-ttu-id="2c1e5-135">По умолчанию удаленные сборки не выполняются в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-135">By default, remote assemblies do not run in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span> <span data-ttu-id="2c1e5-136">Удаленную сборку необходимо запускать с полным доверием или создать для нее изолированный домен <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-136">To run a remote assembly, you must either run it as fully trusted or create a sandboxed <xref:System.AppDomain> in which to run it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c1e5-137">В [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] сборки в общих папках локальной сети выполняются по умолчанию с полным доверием; нет необходимости включать элемент `<loadFromRemoteSources>`.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-137">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], assemblies on local network shares are run as full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c1e5-138">Если приложение скопировано из Интернета, оно помечается ОС Windows как веб-приложение, даже если находится на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-138">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="2c1e5-139">Это обозначение можно изменить, изменив свойства файла, или можно использовать `<loadFromRemoteSources>` элемент для предоставления сборке полное доверие.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-139">You can change that designation by changing the file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="2c1e5-140">Также можно использовать метод <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A>, чтобы загрузить локальную сборку, которую операционная система пометила как загруженную из Интернета.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-140">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>  
  
 <span data-ttu-id="2c1e5-141">`enabled` Атрибута для этого элемента действует только в том случае, при отключении управления доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="2c1e5-141">The `enabled` attribute for this element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="2c1e5-142">По умолчанию политика разграничения доступа кода отключена в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-142">By default, CAS policy is disabled in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later versions.</span></span> <span data-ttu-id="2c1e5-143">Если задать `enabled` для `true`, удаленным приложениям предоставляется полное доверие.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-143">If you set `enabled` to `true`, remote applications are granted full trust.</span></span>  
  
 <span data-ttu-id="2c1e5-144">Если `<loadFromRemoteSources>``enabled` равно `true`, возникает исключение при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="2c1e5-144">If `<loadFromRemoteSources>``enabled` is not set to `true`, an exception is thrown under the following conditions:</span></span>  
  
-   <span data-ttu-id="2c1e5-145">Поведение «песочницы» для текущего домена отличается от его поведения в [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c1e5-145">The sandboxing behavior of the current domain is different from its behavior in the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span> <span data-ttu-id="2c1e5-146">Требуется отключить политики разграничения доступа кода и текущий домен не в песочницу.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-146">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>  
  
-   <span data-ttu-id="2c1e5-147">Загружаемая сборка не из `MyComputer` зоны.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-147">The assembly being loaded is not from the `MyComputer` zone.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c1e5-148">Может возникнуть <xref:System.IO.FileLoadException> в приложении Windows Virtual PC, при попытке загрузить файл из связанного папки на данном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-148">You may get a <xref:System.IO.FileLoadException> in a Windows Virtual PC application when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="2c1e5-149">Эта ошибка также может возникнуть при попытке загрузить файл из папки, заданной через [служб удаленных рабочих столов](http://go.microsoft.com/fwlink/?LinkId=182775) (службы терминалов).</span><span class="sxs-lookup"><span data-stu-id="2c1e5-149">This error may also occur when you try to load a file from a folder linked over [Remote Desktop Services](http://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="2c1e5-150">Чтобы избежать этого исключения, задайте `enabled` для `true`.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-150">To avoid the exception, set `enabled` to `true`.</span></span>  
  
 <span data-ttu-id="2c1e5-151">Установка `<loadFromRemoteSources>` элемент `true` предотвращает это исключение вызывается.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="2c1e5-152">Позволяет указать, что вы не полагаетесь на CLR для "песочницы" загруженных сборок для обеспечения безопасности и что они будет разрешено выполняться как полный уровень доверия.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute as full trust.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2c1e5-153">Если сборки не должно выполняться с полным доверием, не задавайте этот элемент конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-153">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="2c1e5-154">Вместо этого создайте изолированное <xref:System.AppDomain> для загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-154">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="2c1e5-155">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="2c1e5-155">Configuration File</span></span>  
 <span data-ttu-id="2c1e5-156">Этот элемент обычно используется в файле конфигурации приложения, но может использоваться в других файлах конфигурации в зависимости от контекста.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-156">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="2c1e5-157">Дополнительные сведения см. в статье [несколько неявных использует из политики разграничения доступа кода: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) в блоге безопасность платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-157">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c1e5-158">Пример</span><span class="sxs-lookup"><span data-stu-id="2c1e5-158">Example</span></span>  
 <span data-ttu-id="2c1e5-159">В следующем примере показано, как предоставить полное доверие приложениям из удаленных источников.</span><span class="sxs-lookup"><span data-stu-id="2c1e5-159">The following example shows how to grant full trust to applications from remote sources.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c1e5-160">См. также</span><span class="sxs-lookup"><span data-stu-id="2c1e5-160">See Also</span></span>  
 [<span data-ttu-id="2c1e5-161">Более неявного использования политики разграничения доступа кода: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="2c1e5-161">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266839)  
 [<span data-ttu-id="2c1e5-162">Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде</span><span class="sxs-lookup"><span data-stu-id="2c1e5-162">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [<span data-ttu-id="2c1e5-163">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="2c1e5-163">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="2c1e5-164">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="2c1e5-164">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
