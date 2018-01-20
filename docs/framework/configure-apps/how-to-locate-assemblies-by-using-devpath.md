---
title: "Практическое руководство. Поиск сборок с помощью DEVPATH"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 0944f2798c45a039149baaa6e46ce2b56eb5c5df
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="b4b6c-102">Практическое руководство. Поиск сборок с помощью DEVPATH</span><span class="sxs-lookup"><span data-stu-id="b4b6c-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="b4b6c-103">Разработчикам может потребоваться убедитесь в том, что общей сборки, которые они построении правильно работает с несколькими приложениями.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="b4b6c-104">Вместо постоянно помещать сборку в глобальный кэш сборок во время цикла разработки, разработчик может создать переменную среды DEVPATH, которая указывает выходной каталог сборки для сборки.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="b4b6c-105">Например предположим, что вы создаете общей сборки с именем MySharedAssembly и в выходной каталог C:\MySharedAssembly\Debug.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="b4b6c-106">C:\MySharedAssembly\Debug можно поместить в переменной DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="b4b6c-107">Необходимо указать [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) элемент в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="b4b6c-108">Этот элемент предписывает среда использовать DEVPATH для обнаружения сборок.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="b4b6c-109">Эту сборку необходимо обнаруживаемый средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="b4b6c-110">Чтобы указать закрытый каталог для разрешения использования ссылок на сборки [ \<codeBase > элемент](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) или [ \<зондирования > элемент](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) в файле конфигурации, как описано в [Указание расположения сборки](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="b4b6c-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="b4b6c-111">Можно также поместить сборку в подкаталог в каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="b4b6c-112">Дополнительные сведения см. в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="b4b6c-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4b6c-113">Это дополнительная функция, предназначенная только для разработки.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="b4b6c-114">В следующем примере показано, как среда выполнения поиска сборок в каталогах, указанных в переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4b6c-115">Пример</span><span class="sxs-lookup"><span data-stu-id="b4b6c-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="b4b6c-116">Этот параметр по умолчанию используется значение false.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4b6c-117">Используйте этот параметр только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-117">Use this setting only at development time.</span></span> <span data-ttu-id="b4b6c-118">Среда выполнения проверяет версии сборок со строгими именами, в DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="b4b6c-119">Он просто использует первый найденную сборку.</span><span class="sxs-lookup"><span data-stu-id="b4b6c-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b6c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b4b6c-120">See Also</span></span>  
 [<span data-ttu-id="b4b6c-121">Настройка приложений .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b4b6c-121">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
