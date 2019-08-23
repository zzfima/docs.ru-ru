---
title: Указание расположения сборки
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: 43cd1d0edbb607f69f27661aae3372e93564b3b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932334"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="b321d-102">Указание расположения сборки</span><span class="sxs-lookup"><span data-stu-id="b321d-102">Specifying an Assembly's Location</span></span>
<span data-ttu-id="b321d-103">Существует два способа указания расположения сборки:</span><span class="sxs-lookup"><span data-stu-id="b321d-103">There are two ways to specify an assembly's location:</span></span>  
  
- <span data-ttu-id="b321d-104">С помощью элемента [ CodeBase>.\<](./file-schema/runtime/codebase-element.md)</span><span class="sxs-lookup"><span data-stu-id="b321d-104">Using the [\<codeBase>](./file-schema/runtime/codebase-element.md) element.</span></span>  
  
- <span data-ttu-id="b321d-105">С помощью элемента > проверки. [ \<](./file-schema/runtime/probing-element.md)</span><span class="sxs-lookup"><span data-stu-id="b321d-105">Using the [\<probing>](./file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="b321d-106">Можно также использовать [средство настройки .NET Framework (Mscorcfg. msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) , чтобы указать расположения сборок или указать расположения среды CLR для проверки сборок.</span><span class="sxs-lookup"><span data-stu-id="b321d-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="b321d-107">Использование элемента \<CodeBase ></span><span class="sxs-lookup"><span data-stu-id="b321d-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="b321d-108">Элемент  **\<CodeBase >** можно использовать только в конфигурации компьютера или в файлах политики издателя, которые также перенаправляют версию сборки.</span><span class="sxs-lookup"><span data-stu-id="b321d-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="b321d-109">Когда среда выполнения определяет используемую версию сборки, она применяет параметр базы кода из файла, который определяет версию.</span><span class="sxs-lookup"><span data-stu-id="b321d-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="b321d-110">Если не указано ни одной базы кода, среда выполнения проверяет наличие сборки обычным способом.</span><span class="sxs-lookup"><span data-stu-id="b321d-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="b321d-111">Дополнительные сведения см. [в разделе Обнаружение сборок в среде выполнения](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="b321d-111">For details, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="b321d-112">В следующем примере показано, как указать расположение сборки.</span><span class="sxs-lookup"><span data-stu-id="b321d-112">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="b321d-113">Атрибут **Version** необходим для всех сборок со строгими именами, но должен быть опущен для сборок, не имеющих строгих имен.</span><span class="sxs-lookup"><span data-stu-id="b321d-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="b321d-114">**\<CodeBase>** элемента требуется **href** атрибута.</span><span class="sxs-lookup"><span data-stu-id="b321d-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="b321d-115">В элементе CodeBase > нельзя указывать диапазоны версий.  **\<**</span><span class="sxs-lookup"><span data-stu-id="b321d-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b321d-116">Если вы предоставляете указание базы кода для сборки, не имеющей строгого имени, подсказка должна указывать на базу приложения или подкаталог базового каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="b321d-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="b321d-117">\<Использование элемента > зондированием</span><span class="sxs-lookup"><span data-stu-id="b321d-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="b321d-118">Среда выполнения находит сборки, не имеющие базы кода, путем проверки.</span><span class="sxs-lookup"><span data-stu-id="b321d-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="b321d-119">Дополнительные сведения о проверке см. в разделе [как среда выполнения находит сборки](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="b321d-119">For more information about probing, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="b321d-120">Вы можете использовать [ \<](./file-schema/runtime/probing-element.md) элемент проверки > в файле конфигурации приложения, чтобы указать подкаталоги, которые среда выполнения должна искать при поиске сборки.</span><span class="sxs-lookup"><span data-stu-id="b321d-120">You can use the [\<probing>](./file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="b321d-121">В следующем примере показано, как указать каталоги, которые должна искать среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="b321d-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="b321d-122">Атрибут **privatePath** содержит каталоги, в которых среда выполнения должна искать сборки.</span><span class="sxs-lookup"><span data-stu-id="b321d-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="b321d-123">Если приложение расположено в папке C:\Program Files\MyApp, среда выполнения будет искать сборки, не указывающие базу кода в C:\Program Филес\мяпп\бин, C:\Program Files\MyApp\Bin2\Subbin и C:\Program Files\MyApp\Bin3.</span><span class="sxs-lookup"><span data-stu-id="b321d-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="b321d-124">Каталоги, указанные в параметре **privatePath** , должны быть подкаталогами базового каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="b321d-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b321d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b321d-125">See also</span></span>

- [<span data-ttu-id="b321d-126">Сборки в среде CLR</span><span class="sxs-lookup"><span data-stu-id="b321d-126">Assemblies in the Common Language Runtime</span></span>](../app-domains/assemblies-in-the-common-language-runtime.md)
- [<span data-ttu-id="b321d-127">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="b321d-127">Programming with Assemblies</span></span>](../app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="b321d-128">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="b321d-128">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="b321d-129">Настройка приложений с помощью файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="b321d-129">Configuring Apps by using Configuration Files</span></span>](index.md)
