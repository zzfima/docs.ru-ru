---
title: "Практическое руководство. Регистрация основных сборок взаимодействия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- registering primary interop assemblies
- primary interop assemblies, registering
ms.assetid: 4b2fcf8a-429d-43ce-8334-e026040be8bb
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6615abdf621217baa7ced4211bfa19abac944be9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-register-primary-interop-assemblies"></a><span data-ttu-id="e9666-102">Практическое руководство. Регистрация основных сборок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="e9666-102">How to: Register Primary Interop Assemblies</span></span>
<span data-ttu-id="e9666-103">Маршалинг классов может выполняться только с помощью COM-взаимодействия и только в качестве интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="e9666-103">Classes can be marshaled only by COM interop and are always marshaled as interfaces.</span></span> <span data-ttu-id="e9666-104">Иногда интерфейс, используемый для маршалинга класса, называют интерфейсом класса.</span><span class="sxs-lookup"><span data-stu-id="e9666-104">In some cases the interface used to marshal the class is known as the class interface.</span></span> <span data-ttu-id="e9666-105">Сведения о переопределении интерфейса класса выбранным интерфейсом см. в разделе [Вызываемая оболочка COM](../../../docs/framework/interop/com-callable-wrapper.md).</span><span class="sxs-lookup"><span data-stu-id="e9666-105">For information about overriding the class interface with an interface of your choice, see [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md).</span></span>  
  
 <span data-ttu-id="e9666-106">Разработчик, желающий использовать типы COM из приложения .NET Framework, может создать сборку взаимодействия, однако это связано с проблемой.</span><span class="sxs-lookup"><span data-stu-id="e9666-106">Although any developer who wants to use COM types from a .NET Framework application can generate an interop assembly, doing so creates a problem.</span></span> <span data-ttu-id="e9666-107">Каждый раз, когда разработчик импортирует и подписывает библиотеку типов COM, он создает набор уникальных типов, которые несовместимы с типами, импортированными и подписанными другим разработчиком.</span><span class="sxs-lookup"><span data-stu-id="e9666-107">Each time a developer imports and signs a COM type library, that developer creates a set of unique types that are incompatible with those imported and signed by another developer.</span></span> <span data-ttu-id="e9666-108">Чтобы решить эту проблему несовместимости, каждый разработчик должен получить предоставляемую поставщиком и подписанную основную сборку взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e9666-108">The solution to this type incompatibility problem is for each developer to obtain the vendor-supplied and signed primary interop assembly.</span></span>  
  
 <span data-ttu-id="e9666-109">Если вы планируете предоставлять доступ к сторонним типам COM другим приложениям, всегда используйте основную сборку взаимодействия, предоставленную тем же издателем, что и определяемая ею библиотека типов.</span><span class="sxs-lookup"><span data-stu-id="e9666-109">If you plan to expose third-party COM types to other applications, always use the primary interop assembly provided by the same publisher as the type library it defines.</span></span> <span data-ttu-id="e9666-110">Помимо обеспечения гарантированной совместимости типов, основные сборки взаимодействия часто настраиваются поставщиками так, чтобы оптимизировать взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="e9666-110">In addition to providing guaranteed type compatibility, primary interop assemblies are often customized by the vendor to enhance interoperability.</span></span>  
  
 <span data-ttu-id="e9666-111">Даже если вы не планируете предоставлять доступ к сторонним типам COM, использование основной сборки взаимодействия может упростить задачу взаимодействия с COM-компонентами.</span><span class="sxs-lookup"><span data-stu-id="e9666-111">Even if you do not plan to expose third-party COM types, using the primary interop assembly can ease the task of interoperating with COM components.</span></span> <span data-ttu-id="e9666-112">Однако такая стратегия не обеспечивает изоляции от изменений, которые поставщик может вносить в типы, определенные в основной сборке взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e9666-112">However, this strategy provides no insulation from changes a vendor might make to types defined in a primary interop assembly.</span></span> <span data-ttu-id="e9666-113">Если приложению требуется такая изоляция, создайте собственную сборку взаимодействия вместо использования основной сборки взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e9666-113">When your application requires such insulation, generate your own interop assembly instead of using the primary interop assembly.</span></span>  
  
 <span data-ttu-id="e9666-114">Вам необходимо зарегистрировать все приобретенные основные сборки взаимодействия на своем компьютере, прежде чем вы сможете ссылаться на них с помощью [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9666-114">You must register all acquired primary interop assemblies on your development computer before you can reference them with [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)].</span></span> <span data-ttu-id="e9666-115">Visual Studio ищет основную сборку взаимодействия и использует ее при первой ссылке на тип из библиотеки типов COM.</span><span class="sxs-lookup"><span data-stu-id="e9666-115">Visual Studio looks for and uses a primary interop assembly the first time that you reference a type from a COM type library.</span></span> <span data-ttu-id="e9666-116">Если программа Visual Studio не может найти основную сборку взаимодействия, связанную с библиотекой типов, она предлагает приобрести ее или создать сборку взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e9666-116">If Visual Studio cannot locate the primary interop assembly associated with the type library, it prompts you to acquire it or offers to create an interop assembly instead.</span></span> <span data-ttu-id="e9666-117">[Средство импорта библиотек типов (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) также использует реестр для обнаружения основных сборок взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e9666-117">Likewise, the [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) also uses the registry to locate primary interop assemblies.</span></span>  
  
 <span data-ttu-id="e9666-118">Если вы не планируете использовать Visual Studio, регистрировать основные сборки взаимодействия необязательно, однако регистрация предоставляет два преимущества.</span><span class="sxs-lookup"><span data-stu-id="e9666-118">Although it is not necessary to register primary interop assemblies unless you plan to use Visual Studio, registration provides two advantages:</span></span>  
  
-   <span data-ttu-id="e9666-119">Зарегистрированная основная сборка взаимодействия явным образом помечается в разделе реестра исходной библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="e9666-119">A registered primary interop assembly is clearly marked under the registry key of the original type library.</span></span> <span data-ttu-id="e9666-120">Регистрация — наилучший способ обнаружения основной сборки взаимодействия на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e9666-120">Registration is the best way for you to locate a primary interop assembly on your computer.</span></span>  
  
-   <span data-ttu-id="e9666-121">Использование Visual Studio для ссылки на тип, для которого существует незарегистрированная основная сборка взаимодействия, позволяет избежать случайного создания и использования новой сборки взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e9666-121">You can avoid accidentally generating and using a new interop assembly if, at some time in the future, you do use Visual Studio to reference a type for which you have an unregistered primary interop assembly.</span></span>  
  
 <span data-ttu-id="e9666-122">Для регистрации основной сборки взаимодействия используется [средство регистрации сборок (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md).</span><span class="sxs-lookup"><span data-stu-id="e9666-122">Use the [Assembly Registration Tool (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) to register a primary interop assembly.</span></span>  
  
### <a name="to-register-a-primary-interop-assembly"></a><span data-ttu-id="e9666-123">Регистрация основной сборки взаимодействия</span><span class="sxs-lookup"><span data-stu-id="e9666-123">To register a primary interop assembly</span></span>  
  
1.  <span data-ttu-id="e9666-124">В командной строке введите следующее:</span><span class="sxs-lookup"><span data-stu-id="e9666-124">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="e9666-125">**regasm** *имя_сборки*</span><span class="sxs-lookup"><span data-stu-id="e9666-125">**regasm** *assemblyname*</span></span>  
  
     <span data-ttu-id="e9666-126">В этой команде *имя_сборки* — это имя файла регистрируемой сборки.</span><span class="sxs-lookup"><span data-stu-id="e9666-126">In this command, *assemblyname* is the file name of the assembly that is registered.</span></span> <span data-ttu-id="e9666-127">Программа Regasm.exe добавляет запись об основной сборке взаимодействия в тот же раздел реестра, что и для исходной библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="e9666-127">Regasm.exe adds an entry for the primary interop assembly under the same registry key as the original type library.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9666-128">Пример</span><span class="sxs-lookup"><span data-stu-id="e9666-128">Example</span></span>  
 <span data-ttu-id="e9666-129">В примере ниже регистрируется основная сборка взаимодействия `CompanyA.UtilLib.dll`.</span><span class="sxs-lookup"><span data-stu-id="e9666-129">The following example registers the `CompanyA.UtilLib.dll` primary interop assembly.</span></span>  
  
```  
regasm CompanyA.UtilLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9666-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e9666-130">See Also</span></span>  
 [<span data-ttu-id="e9666-131">Программирование с использованием основных сборок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="e9666-131">Programming with Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/306fa1d6-0703-4004-9e93-d0a57f1be81e)  
 [<span data-ttu-id="e9666-132">Обнаружение основных сборок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="e9666-132">Locating Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/d6768e4b-cd80-414d-a4f8-05d979eb393b)  
 [<span data-ttu-id="e9666-133">Распространение основных сборок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="e9666-133">Redistributing Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/e76384f0-d631-474c-bdbd-13884cba0265)
