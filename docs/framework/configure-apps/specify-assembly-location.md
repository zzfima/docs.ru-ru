---
title: Указание сборки&#39;расположения
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: 4b5d732eb669119e346c61dce29b579911798edf
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083578"
---
# <a name="specifying-an-assembly39s-location"></a><span data-ttu-id="ee8b9-102">Указание сборки&#39;расположения</span><span class="sxs-lookup"><span data-stu-id="ee8b9-102">Specifying an Assembly&#39;s Location</span></span>
<span data-ttu-id="ee8b9-103">Указание расположения сборки двумя способами:</span><span class="sxs-lookup"><span data-stu-id="ee8b9-103">There are two ways to specify an assembly's location:</span></span>  
  
-   <span data-ttu-id="ee8b9-104">С помощью [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-104">Using the [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) element.</span></span>  
  
-   <span data-ttu-id="ee8b9-105">С помощью [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-105">Using the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="ee8b9-106">Можно также использовать [средством настройки .NET Framework (Mscorcfg.msc)](https://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) чтобы задавать расположение сборки или расположения для среда поиск сборок.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="ee8b9-107">С помощью \<codeBase > элемент</span><span class="sxs-lookup"><span data-stu-id="ee8b9-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="ee8b9-108">Можно использовать  **\<codeBase >** элемент только в машине конфигурации или файле политики издателя, которые также предоставляют перенаправление версии сборки.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="ee8b9-109">Среда выполнения определяет, какие версии сборки, применяется параметр базы кода из файла, который определяет версию.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="ee8b9-110">Если база кода не указана, среда выполняет поиск сборки обычным способом.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="ee8b9-111">Дополнительные сведения см. в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="ee8b9-111">For details, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="ee8b9-112">В следующем примере показано, как указание расположения сборки.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-112">The following example shows how to specify an assembly's location.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="ee8b9-113">**Версии** атрибут является обязательным для всех сборок со строгими именами, но должен быть опущен для сборок, которые не имеют строгие имена.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="ee8b9-114"> *\*\<CodeBase >** элемента требуется *\*href** атрибута.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="ee8b9-115">Нельзя указать диапазон версий в  **\<codeBase >** элемент.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee8b9-116">Если вы указали подсказка базы кода для сборки, не является строгим именем, должна указывать на базовой папки приложения или ее подкаталог базового каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="ee8b9-117">С помощью \<probing > элемент</span><span class="sxs-lookup"><span data-stu-id="ee8b9-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="ee8b9-118">Среда выполнения находит сборки, у которых нет базы кода при проверке.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="ee8b9-119">Дополнительные сведения о проверке см. в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="ee8b9-119">For more information about probing, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="ee8b9-120">Можно использовать [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) элемент в файле конфигурации приложения для указания подкаталогов, среда выполнения должна использовать при определении расположения сборки.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-120">You can use the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="ee8b9-121">В следующем примере показано, как можно указать каталоги, которые среда выполнения должна выполнять поиск.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="ee8b9-122">**PrivatePath** атрибут содержит каталоги, которые среда выполнения должна искать сборки.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="ee8b9-123">Если приложение находится в каталоге C:\Program Files\MyApp, среда выполнения ищет сборки, которые не указаны базы кода в C:\Program Files\MyApp\Bin C:\Program Files\MyApp\Bin2\Subbin и C:\Program Files\MyApp\Bin3.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="ee8b9-124">Каталоги, указанные в **privatePath** должны быть подкаталогами базового каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="ee8b9-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee8b9-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ee8b9-125">See also</span></span>
- [<span data-ttu-id="ee8b9-126">Сборки в среде CLR</span><span class="sxs-lookup"><span data-stu-id="ee8b9-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [<span data-ttu-id="ee8b9-127">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="ee8b9-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="ee8b9-128">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="ee8b9-128">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="ee8b9-129">Настройка приложений .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ee8b9-129">Configuring .NET Framework Apps</span></span>](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
