---
title: "COM-взаимодействие без регистрации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], interop
- COM interop, registration-free COM interop
- registration-free COM interop
- manifests [.NET Framework]
- registration-free activation
- object activation
- registration-free COM interop, about registration-free COM interop
ms.assetid: 90f308b9-82dc-414a-bce1-77e0155e56bd
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1eee55b2036028dd491dc82f9bce7c51aca878fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="registration-free-com-interop"></a><span data-ttu-id="5bb75-102">COM-взаимодействие без регистрации</span><span class="sxs-lookup"><span data-stu-id="5bb75-102">Registration-Free COM Interop</span></span>
<span data-ttu-id="5bb75-103">COM-взаимодействие без регистрации активирует компонент, не используя реестр Windows для хранения сведений о сборке.</span><span class="sxs-lookup"><span data-stu-id="5bb75-103">Registration-free COM interop activates a component without using the Windows registry to store assembly information.</span></span> <span data-ttu-id="5bb75-104">Вместо регистрации компонента на компьютере во время развертывания необходимо в режиме разработки создать файлы манифеста в стиле Win32, содержащие информацию о привязке и активации.</span><span class="sxs-lookup"><span data-stu-id="5bb75-104">Instead of registering a component on a computer during deployment, you create Win32-style manifest files at design time that contain information about binding and activation.</span></span> <span data-ttu-id="5bb75-105">Именно эти файлы манифеста, а не ключи реестра, управляют активацией объекта.</span><span class="sxs-lookup"><span data-stu-id="5bb75-105">These manifest files, rather than registry keys, direct the activation of an object.</span></span>  
  
 <span data-ttu-id="5bb75-106">Активация сборок без регистрации имеет два преимущества по сравнению с регистрацией во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="5bb75-106">Using registration-free activation for your assemblies instead of registering them during deployment offers two advantages:</span></span>  
  
-   <span data-ttu-id="5bb75-107">Вы можете выбирать активируемую версию библиотеки DLL, если на компьютере установлено несколько версий.</span><span class="sxs-lookup"><span data-stu-id="5bb75-107">You can control which DLL version is activated when more than one version is installed on a computer.</span></span>  
  
-   <span data-ttu-id="5bb75-108">Конечные пользователи могут с помощью XCOPY или FTP скопировать приложение в нужную папку на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="5bb75-108">End users can use XCOPY or FTP to copy your application to an appropriate directory on their computer.</span></span> <span data-ttu-id="5bb75-109">Затем приложение можно будет запустить из этой папки.</span><span class="sxs-lookup"><span data-stu-id="5bb75-109">The application can then be run from that directory.</span></span>  
  
 <span data-ttu-id="5bb75-110">В этом разделе описываются два типа манифестов, которые требуются для COM-взаимодействия без регистрации: манифесты приложений и манифесты компонентов.</span><span class="sxs-lookup"><span data-stu-id="5bb75-110">This section describes the two types of manifests needed for registration-free COM interop: application and component manifests.</span></span> <span data-ttu-id="5bb75-111">Эти манифесты являются файлами XML.</span><span class="sxs-lookup"><span data-stu-id="5bb75-111">These manifests are XML files.</span></span> <span data-ttu-id="5bb75-112">Манифест приложения, создаваемый разработчиком приложения, содержит метаданные, которые описывают сборки и зависимости сборок.</span><span class="sxs-lookup"><span data-stu-id="5bb75-112">An application manifest, which is created by an application developer, contains metadata that describes assemblies and assembly dependencies.</span></span> <span data-ttu-id="5bb75-113">Манифест компонента, создаваемый разработчиком компонента, содержит сведения, которые обычно находятся в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="5bb75-113">A component manifest, created by a component developer, contains information otherwise located in the Windows registry.</span></span>  
  
### <a name="requirements-for-registration-free-com-interop"></a><span data-ttu-id="5bb75-114">Требования для COM-взаимодействия без регистрации</span><span class="sxs-lookup"><span data-stu-id="5bb75-114">Requirements for registration-free COM interop</span></span>  
  
1.  <span data-ttu-id="5bb75-115">Поддержка COM-взаимодействия без регистрации немного различается в зависимости от типа сборки библиотеки. В частности, она зависит от того, является ли сборка неуправляемой (параллельный COM) или управляемой (на основе .NET).</span><span class="sxs-lookup"><span data-stu-id="5bb75-115">Support for registration-free COM interop varies slightly depending on the type of library assembly; specifically, whether the assembly is unmanaged (COM side-by-side) or managed (.NET-based).</span></span> <span data-ttu-id="5bb75-116">В таблице ниже приведены требования к версии операционной системы и платформы .NET Framework для каждого типа сборки.</span><span class="sxs-lookup"><span data-stu-id="5bb75-116">The following table shows the operating system and .NET Framework version requirements for each assembly type.</span></span>  
  
    |<span data-ttu-id="5bb75-117">Тип сборки</span><span class="sxs-lookup"><span data-stu-id="5bb75-117">Assembly type</span></span>|<span data-ttu-id="5bb75-118">Операционная система</span><span class="sxs-lookup"><span data-stu-id="5bb75-118">Operating system</span></span>|<span data-ttu-id="5bb75-119">Версия платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5bb75-119">.NET Framework version</span></span>|  
    |-------------------|----------------------|----------------------------|  
    |<span data-ttu-id="5bb75-120">Параллельный COM</span><span class="sxs-lookup"><span data-stu-id="5bb75-120">COM side-by-side</span></span>|<span data-ttu-id="5bb75-121">Microsoft Windows XP</span><span class="sxs-lookup"><span data-stu-id="5bb75-121">Microsoft Windows XP</span></span>|<span data-ttu-id="5bb75-122">Не требуется.</span><span class="sxs-lookup"><span data-stu-id="5bb75-122">Not required.</span></span>|  
    |<span data-ttu-id="5bb75-123">На базе .NET</span><span class="sxs-lookup"><span data-stu-id="5bb75-123">.NET-based</span></span>|<span data-ttu-id="5bb75-124">Windows XP с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="5bb75-124">Windows XP with SP2</span></span>|<span data-ttu-id="5bb75-125">.NET Framework версии 1.1 или более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="5bb75-125">NET Framework version 1.1 or later.</span></span>|  
  
     <span data-ttu-id="5bb75-126">Продукты семейства Windows Server 2003 также поддерживают COM-взаимодействие без регистрации для сборок на основе .NET.</span><span class="sxs-lookup"><span data-stu-id="5bb75-126">The Windows Server 2003 family also supports registration-free COM interop for .NET-based assemblies.</span></span>  
  
     <span data-ttu-id="5bb75-127">Чтобы класс на основе .NET был совместим с активацией без регистрации из COM, он должен быть открытым и у него должен быть конструктор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5bb75-127">For a .NET-based class to be compatible with registry-free activation from COM, the class must have a default constructor and must be public.</span></span>  
  
### <a name="configuring-com-components-for-registration-free-activation"></a><span data-ttu-id="5bb75-128">Настройка COM-компонентов для активации без регистрации</span><span class="sxs-lookup"><span data-stu-id="5bb75-128">Configuring COM components for registration-free activation</span></span>  
  
1.  <span data-ttu-id="5bb75-129">Чтобы COM-компонент участвовал в активации без регистрации, его необходимо развернуть как параллельную сборку.</span><span class="sxs-lookup"><span data-stu-id="5bb75-129">For a COM component to participate in registration-free activation, it must be deployed as a side-by-side assembly.</span></span> <span data-ttu-id="5bb75-130">Параллельные сборки являются неуправляемыми.</span><span class="sxs-lookup"><span data-stu-id="5bb75-130">Side-by-side assemblies are unmanaged assemblies.</span></span>  <span data-ttu-id="5bb75-131">Дополнительные сведения см. в разделе [использование сборок Side-by-side](https://msdn.microsoft.com/library/windows/desktop/aa376618.aspx).</span><span class="sxs-lookup"><span data-stu-id="5bb75-131">For more information, see [Using Side-by-side Assemblies](https://msdn.microsoft.com/library/windows/desktop/aa376618.aspx).</span></span>  
  
     <span data-ttu-id="5bb75-132">Чтобы использовать параллельные сборки COM, разработчик приложения на основе .NET должен предоставить манифест приложения, содержащий информацию о привязке и активации.</span><span class="sxs-lookup"><span data-stu-id="5bb75-132">To use COM side-by-side assemblies, a .NET-based application developer must provide an application manifest, which contains the binding and activation information.</span></span> <span data-ttu-id="5bb75-133">Поддержка неуправляемых параллельных сборок встроена в операционную систему Windows XP.</span><span class="sxs-lookup"><span data-stu-id="5bb75-133">Support for unmanaged side-by-side assemblies is built into the Windows XP operating system.</span></span> <span data-ttu-id="5bb75-134">Среда выполнения COM, поддерживаемая операционной системой, просматривает манифест приложения в поисках информации об активации, если активируемый компонент не занесен в реестр.</span><span class="sxs-lookup"><span data-stu-id="5bb75-134">The COM runtime, supported by the operating system, scans an application manifest for activation information when the component being activated is not in the registry.</span></span>  
  
     <span data-ttu-id="5bb75-135">Активация без регистрации не является обязательной для COM-компонентов, установленных в ОС Windows XP.</span><span class="sxs-lookup"><span data-stu-id="5bb75-135">Registration-free activation is optional for COM components installed on Windows XP.</span></span> <span data-ttu-id="5bb75-136">Подробные инструкции о добавлении side-by-side сборки в приложение см. в разделе [использование сборок Side-by-side](https://msdn.microsoft.com/library/windows/desktop/aa376618.aspx).</span><span class="sxs-lookup"><span data-stu-id="5bb75-136">For detailed instructions on adding a side-by-side assembly to an application, see [Using Side-by-side Assemblies](https://msdn.microsoft.com/library/windows/desktop/aa376618.aspx).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5bb75-137">Параллельное выполнение — это функциональная возможность .NET Framework, которая позволяет одновременно работать на компьютере нескольким версиям среды выполнения и нескольким версиям приложений и компонентов, использующим одну из версий среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="5bb75-137">Side-by-side execution is a .NET Framework feature that enables multiple versions of the runtime, and multiple versions of applications and components that use a version of the runtime, to run on the same computer at the same time.</span></span> <span data-ttu-id="5bb75-138">Параллельное выполнение и параллельные сборки — это разные механизмы обеспечения параллельной работы.</span><span class="sxs-lookup"><span data-stu-id="5bb75-138">Side-by-side execution and side-by-side assemblies are different mechanisms for providing side-by-side functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb75-139">См. также</span><span class="sxs-lookup"><span data-stu-id="5bb75-139">See Also</span></span>  
 [<span data-ttu-id="5bb75-140">Практическое руководство. Настройка COM-компонентов на основе платформы .NET Framework для активации без регистрации</span><span class="sxs-lookup"><span data-stu-id="5bb75-140">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>](../../../docs/framework/interop/configure-net-framework-based-com-components-for-reg.md)
