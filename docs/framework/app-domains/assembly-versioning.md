---
title: "Управление версиями сборок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- informational versions
- version numbers, assemblies
- assemblies [.NET Framework], versioning
- resolving assembly binding requests
- versioning, assemblies
ms.assetid: 775ad4fb-914f-453c-98ef-ce1089b6f903
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 327ef282c23fc02791eb7c531fd1ae25c6700fd4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="assembly-versioning"></a><span data-ttu-id="a18ad-102">Управление версиями сборок</span><span class="sxs-lookup"><span data-stu-id="a18ad-102">Assembly Versioning</span></span>
<span data-ttu-id="a18ad-103">Управление версиями сборок, использующих среду CLR, производится полностью на уровне сборки.</span><span class="sxs-lookup"><span data-stu-id="a18ad-103">All versioning of assemblies that use the common language runtime is done at the assembly level.</span></span> <span data-ttu-id="a18ad-104">Конкретная версия сборки и версии зависимых от нее сборок указываются в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="a18ad-104">The specific version of an assembly and the versions of dependent assemblies are recorded in the assembly's manifest.</span></span> <span data-ttu-id="a18ad-105">Политика управления версиями по умолчанию для среды выполнения заключается в том, что приложения могут выполняться только с версиями, с которыми они были разработаны и протестированы, если иное не переопределено явной политикой использования версий в файлах конфигурации (в файле конфигурации приложения, файле политики издателя и файле конфигурации администратора компьютера).</span><span class="sxs-lookup"><span data-stu-id="a18ad-105">The default version policy for the runtime is that applications run only with the versions they were built and tested with, unless overridden by explicit version policy in configuration files (the application configuration file, the publisher policy file, and the computer's administrator configuration file).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a18ad-106">Управление версиями выполняется только для сборок со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="a18ad-106">Versioning is done only on assemblies with strong names.</span></span>  
  
 <span data-ttu-id="a18ad-107">Среда выполнения предпринимает несколько шагов для разрешения запроса привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="a18ad-107">The runtime performs several steps to resolve an assembly binding request:</span></span>  
  
1.  <span data-ttu-id="a18ad-108">Проверяет исходную ссылку на сборку для определения версии сборки, с которой будет связано приложение.</span><span class="sxs-lookup"><span data-stu-id="a18ad-108">Checks the original assembly reference to determine the version of the assembly to be bound.</span></span>  
  
2.  <span data-ttu-id="a18ad-109">Проверяет все применимые файлы конфигурации для использования политики управления версиями.</span><span class="sxs-lookup"><span data-stu-id="a18ad-109">Checks for all applicable configuration files to apply version policy.</span></span>  
  
3.  <span data-ttu-id="a18ad-110">Определяет правильную сборку на основании исходной ссылки на сборку и любого указанного в файлах конфигурации перенаправления, а также версию, которая должна связываться с вызывающей сборкой.</span><span class="sxs-lookup"><span data-stu-id="a18ad-110">Determines the correct assembly from the original assembly reference and any redirection specified in the configuration files, and determines the version that should be bound to the calling assembly.</span></span>  
  
4.  <span data-ttu-id="a18ad-111">Проверяет глобальный кэш сборок и указанные в файлах конфигурации базы кода, а затем проверяет папку приложения и вложенные папки с помощью правил проверки, описанных в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="a18ad-111">Checks the global assembly cache, codebases specified in configuration files, and then checks the application's directory and subdirectories using the probing rules explained in [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="a18ad-112">Указанные шаги показаны на следующей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="a18ad-112">The following illustration shows these steps.</span></span>  
  
 <span data-ttu-id="a18ad-113">![сборка, расширяющая myAssembly](../../../docs/framework/app-domains/media/versioningover.gif "versioningover")</span><span class="sxs-lookup"><span data-stu-id="a18ad-113">![.assembly extern myAssembly](../../../docs/framework/app-domains/media/versioningover.gif "versioningover")</span></span>  
<span data-ttu-id="a18ad-114">Разрешение запроса привязки сборки</span><span class="sxs-lookup"><span data-stu-id="a18ad-114">Resolving an assembly binding request</span></span>  
  
 <span data-ttu-id="a18ad-115">Дополнительные сведения о настройке приложений см. в разделе [Настройка приложений](../../../docs/framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="a18ad-115">For more information about configuring applications, see [Configuring Apps](../../../docs/framework/configure-apps/index.md).</span></span> <span data-ttu-id="a18ad-116">Дополнительные сведения о политике привязки см. в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="a18ad-116">For more information about binding policy, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
## <a name="version-information"></a><span data-ttu-id="a18ad-117">Сведения о версии</span><span class="sxs-lookup"><span data-stu-id="a18ad-117">Version Information</span></span>  
 <span data-ttu-id="a18ad-118">В каждой сборке есть два различных способа задания сведений о версии.</span><span class="sxs-lookup"><span data-stu-id="a18ad-118">Each assembly has two distinct ways of expressing version information:</span></span>  
  
-   <span data-ttu-id="a18ad-119">Номер версии сборки, который наряду с именем сборки и сведениями о языке и региональных параметрах является частью удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="a18ad-119">The assembly's version number, which, together with the assembly name and culture information, is part of the assembly's identity.</span></span> <span data-ttu-id="a18ad-120">Это номер используется средой выполнения для применения политики управления версиями и играет ключевую роль в процессе разрешения типов на этапе выполнения.</span><span class="sxs-lookup"><span data-stu-id="a18ad-120">This number is used by the runtime to enforce version policy and plays a key part in the type resolution process at run time.</span></span>  
  
-   <span data-ttu-id="a18ad-121">Информационная версия, которая представляет собой строку с дополнительными сведениями о версии, служащую исключительно в информационных целях.</span><span class="sxs-lookup"><span data-stu-id="a18ad-121">An informational version, which is a string that represents additional version information included for informational purposes only.</span></span>  
  
### <a name="assembly-version-number"></a><span data-ttu-id="a18ad-122">Номер версии сборки</span><span class="sxs-lookup"><span data-stu-id="a18ad-122">Assembly Version Number</span></span>  
 <span data-ttu-id="a18ad-123">Каждая сборка имеет номер версии, являющийся частью ее удостоверения.</span><span class="sxs-lookup"><span data-stu-id="a18ad-123">Each assembly has a version number as part of its identity.</span></span> <span data-ttu-id="a18ad-124">Следовательно, две сборки, имеющие разные номера версий, рассматриваются средой выполнения как совершенно разные сборки.</span><span class="sxs-lookup"><span data-stu-id="a18ad-124">As such, two assemblies that differ by version number are considered by the runtime to be completely different assemblies.</span></span> <span data-ttu-id="a18ad-125">Этот номер версии физически представляется в виде строки из четырех частей следующего формата:</span><span class="sxs-lookup"><span data-stu-id="a18ad-125">This version number is physically represented as a four-part string with the following format:</span></span>  
  
 <span data-ttu-id="a18ad-126">\<*основной номер версии*>.\< *дополнительный номер версии*>.\< *номер сборки*>.\< *номер редакции*></span><span class="sxs-lookup"><span data-stu-id="a18ad-126">\<*major version*>.\<*minor version*>.\<*build number*>.\<*revision*></span></span>  
  
 <span data-ttu-id="a18ad-127">Например, в версии "1.5.1254.0" число "1" представляет основную версию, "5" — младший номер версии, "1254" — номер построения, а "0" — номер редакции.</span><span class="sxs-lookup"><span data-stu-id="a18ad-127">For example, version 1.5.1254.0 indicates 1 as the major version, 5 as the minor version, 1254 as the build number, and 0 as the revision number.</span></span>  
  
 <span data-ttu-id="a18ad-128">Номер версии сохраняется в манифесте сборки вместе с другими данными удостоверения, включая имя сборки и открытый ключ, а также сведения о связях и удостоверениях других подключаемых к приложению сборок.</span><span class="sxs-lookup"><span data-stu-id="a18ad-128">The version number is stored in the assembly manifest along with other identity information, including the assembly name and public key, as well as information on relationships and identities of other assemblies connected with the application.</span></span>  
  
 <span data-ttu-id="a18ad-129">При построении сборки средство разработки записывает сведения о зависимостях каждой сборки, на которую имеется ссылка, в манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="a18ad-129">When an assembly is built, the development tool records dependency information for each assembly that is referenced in the assembly manifest.</span></span> <span data-ttu-id="a18ad-130">Среда выполнения использует эти номера версий вместе с конфигурационными данными, установленными администратором, приложением или издателем для загрузки нужной версии сборки, на которую имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="a18ad-130">The runtime uses these version numbers, in conjunction with configuration information set by an administrator, an application, or a publisher, to load the proper version of a referenced assembly.</span></span>  
  
 <span data-ttu-id="a18ad-131">С целью управления версиями среда выполнения разделяет обычные сборки и сборки со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="a18ad-131">The runtime distinguishes between regular and strong-named assemblies for the purposes of versioning.</span></span> <span data-ttu-id="a18ad-132">Проверка версий производится только для сборок со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="a18ad-132">Version checking only occurs with strong-named assemblies.</span></span>  
  
 <span data-ttu-id="a18ad-133">Сведения о политиках привязки версий см. в разделе [Настройка приложений](../../../docs/framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="a18ad-133">For information about specifying version binding policies, see [Configuring Apps](../../../docs/framework/configure-apps/index.md).</span></span> <span data-ttu-id="a18ad-134">Дополнительные сведения о способе использования средой выполнения сведений о версии для поиска определенной сборки см. в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="a18ad-134">For information about how the runtime uses version information to find a particular assembly, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
### <a name="assembly-informational-version"></a><span data-ttu-id="a18ad-135">Информационная версия сборки</span><span class="sxs-lookup"><span data-stu-id="a18ad-135">Assembly Informational Version</span></span>  
 <span data-ttu-id="a18ad-136">Информационная версия сборки представляет собой строку, которая добавляет к сборке дополнительные данные и служит только для информации. Она не используется на этапе выполнения.</span><span class="sxs-lookup"><span data-stu-id="a18ad-136">The informational version is a string that attaches additional version information to an assembly for informational purposes only; this information is not used at run time.</span></span> <span data-ttu-id="a18ad-137">Информационная версия (в текстовом формате) соответствует описанию продукта на рынке, данным о комплектации или названии продукта. Эта версия не используется средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="a18ad-137">The text-based informational version corresponds to the product's marketing literature, packaging, or product name and is not used by the runtime.</span></span> <span data-ttu-id="a18ad-138">Так, информационная версия может быть задана как "Среда CLR версии 1.0" или "Элемент управления NET с пакетом обновления 2".</span><span class="sxs-lookup"><span data-stu-id="a18ad-138">For example, an informational version could be "Common Language Runtime version 1.0" or "NET Control SP 2".</span></span> <span data-ttu-id="a18ad-139">В Microsoft Windows эта информация отображается в элементе "Версия продукта" на вкладке "Версии" в диалоговом окне свойств файла.</span><span class="sxs-lookup"><span data-stu-id="a18ad-139">On the Version tab of the file properties dialog in Microsoft Windows, this information appears in the item "Product Version".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a18ad-140">Хотя можно задать любой текст, при компиляции появится предупреждение, если строка имеет формат отличный от формата номера версии сборки или если она имеет правильный формат, но содержит подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a18ad-140">Although you can specify any text, a warning message appears on compilation if the string is not in the format used by the assembly version number, or if it is in that format but contains wildcards.</span></span> <span data-ttu-id="a18ad-141">Это не опасное предупреждение.</span><span class="sxs-lookup"><span data-stu-id="a18ad-141">This warning is harmless.</span></span>  
  
 <span data-ttu-id="a18ad-142">Информационная версия представляется с помощью пользовательского атрибута <xref:System.Reflection.AssemblyInformationalVersionAttribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a18ad-142">The informational version is represented using the custom attribute <xref:System.Reflection.AssemblyInformationalVersionAttribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a18ad-143">Дополнительные сведения об атрибуте информационной версии см. в разделе [Настройка атрибутов сборки](../../../docs/framework/app-domains/set-assembly-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="a18ad-143">For more information about the informational version attribute, see [Setting Assembly Attributes](../../../docs/framework/app-domains/set-assembly-attributes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a18ad-144">См. также</span><span class="sxs-lookup"><span data-stu-id="a18ad-144">See Also</span></span>  
 [<span data-ttu-id="a18ad-145">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="a18ad-145">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="a18ad-146">Настройка приложений</span><span class="sxs-lookup"><span data-stu-id="a18ad-146">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)  
 [<span data-ttu-id="a18ad-147">Настройка атрибутов сборки</span><span class="sxs-lookup"><span data-stu-id="a18ad-147">Setting Assembly Attributes</span></span>](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 [<span data-ttu-id="a18ad-148">Сборки в среде CLR</span><span class="sxs-lookup"><span data-stu-id="a18ad-148">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
