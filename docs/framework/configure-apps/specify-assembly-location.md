---
title: Указание расположения сборки
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: f7d09e315f2ccc7ecdcf22719ca6dce1ee1411b4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186294"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="28845-102">Указание расположения сборки</span><span class="sxs-lookup"><span data-stu-id="28845-102">Specifying an Assembly's Location</span></span>
<span data-ttu-id="28845-103">Указание расположения сборки двумя способами:</span><span class="sxs-lookup"><span data-stu-id="28845-103">There are two ways to specify an assembly's location:</span></span>  
  
-   <span data-ttu-id="28845-104">С помощью [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="28845-104">Using the [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) element.</span></span>  
  
-   <span data-ttu-id="28845-105">С помощью [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="28845-105">Using the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="28845-106">Можно также использовать [средством настройки .NET Framework (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) чтобы задавать расположение сборки или расположения для среда поиск сборок.</span><span class="sxs-lookup"><span data-stu-id="28845-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="28845-107">С помощью \<codeBase > элемент</span><span class="sxs-lookup"><span data-stu-id="28845-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="28845-108">Можно использовать  **\<codeBase >** элемент только в машине конфигурации или файле политики издателя, которые также предоставляют перенаправление версии сборки.</span><span class="sxs-lookup"><span data-stu-id="28845-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="28845-109">Среда выполнения определяет, какие версии сборки, применяется параметр базы кода из файла, который определяет версию.</span><span class="sxs-lookup"><span data-stu-id="28845-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="28845-110">Если база кода не указана, среда выполняет поиск сборки обычным способом.</span><span class="sxs-lookup"><span data-stu-id="28845-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="28845-111">Дополнительные сведения см. в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="28845-111">For details, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="28845-112">В следующем примере показано, как указание расположения сборки.</span><span class="sxs-lookup"><span data-stu-id="28845-112">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="28845-113">**Версии** атрибут является обязательным для всех сборок со строгими именами, но должен быть опущен для сборок, которые не имеют строгие имена.</span><span class="sxs-lookup"><span data-stu-id="28845-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="28845-114"> *\*\<CodeBase >** элемента требуется *\*href** атрибута.</span><span class="sxs-lookup"><span data-stu-id="28845-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="28845-115">Нельзя указать диапазон версий в  **\<codeBase >** элемент.</span><span class="sxs-lookup"><span data-stu-id="28845-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28845-116">Если вы указали подсказка базы кода для сборки, не является строгим именем, должна указывать на базовой папки приложения или ее подкаталог базового каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="28845-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="28845-117">С помощью \<probing > элемент</span><span class="sxs-lookup"><span data-stu-id="28845-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="28845-118">Среда выполнения находит сборки, у которых нет базы кода при проверке.</span><span class="sxs-lookup"><span data-stu-id="28845-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="28845-119">Дополнительные сведения о проверке см. в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="28845-119">For more information about probing, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="28845-120">Можно использовать [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) элемент в файле конфигурации приложения для указания подкаталогов, среда выполнения должна использовать при определении расположения сборки.</span><span class="sxs-lookup"><span data-stu-id="28845-120">You can use the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="28845-121">В следующем примере показано, как можно указать каталоги, которые среда выполнения должна выполнять поиск.</span><span class="sxs-lookup"><span data-stu-id="28845-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="28845-122">**PrivatePath** атрибут содержит каталоги, которые среда выполнения должна искать сборки.</span><span class="sxs-lookup"><span data-stu-id="28845-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="28845-123">Если приложение находится в каталоге C:\Program Files\MyApp, среда выполнения ищет сборки, которые не указаны базы кода в C:\Program Files\MyApp\Bin C:\Program Files\MyApp\Bin2\Subbin и C:\Program Files\MyApp\Bin3.</span><span class="sxs-lookup"><span data-stu-id="28845-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="28845-124">Каталоги, указанные в **privatePath** должны быть подкаталогами базового каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="28845-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28845-125">См. также</span><span class="sxs-lookup"><span data-stu-id="28845-125">See also</span></span>

- [<span data-ttu-id="28845-126">Сборки в среде CLR</span><span class="sxs-lookup"><span data-stu-id="28845-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [<span data-ttu-id="28845-127">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="28845-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="28845-128">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="28845-128">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="28845-129">Настройка приложений с помощью файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="28845-129">Configuring Apps by using Configuration Files</span></span>](index.md)
