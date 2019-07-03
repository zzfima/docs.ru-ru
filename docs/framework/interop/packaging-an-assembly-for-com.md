---
title: Упаковка сборки для модели COM
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, packaging assemblies
- packaging assemblies for COM
- Tlbexp.exe
- TypeLibConverter class
- .NET Services Installation tool
- Assembly Registration tool
- Type Library Exporter
- Reqsvcs.exe
- interoperation with unmanaged code, exposing .NET Framework components
- interoperation with unmanaged code, packaging assemblies
- COM interop, exposing COM components
- Reqasm.exe
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6933aa5ee253f78806aba401749256934f490126
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833597"
---
# <a name="packaging-an-assembly-for-com"></a><span data-ttu-id="7ec7a-102">Упаковка сборки для модели COM</span><span class="sxs-lookup"><span data-stu-id="7ec7a-102">Packaging an Assembly for COM</span></span>

<span data-ttu-id="7ec7a-103">Разработчики приложений на основе модели COM могут использовать следующую информацию об управляемых типах, которые они планируют включать в свои приложения:</span><span class="sxs-lookup"><span data-stu-id="7ec7a-103">COM developers can benefit from the following information about the managed types they plan to incorporate in their application:</span></span>

- <span data-ttu-id="7ec7a-104">Список типов, которые можно использовать в приложениях на основе модели COM</span><span class="sxs-lookup"><span data-stu-id="7ec7a-104">A list of types that COM applications can consume</span></span>

  <span data-ttu-id="7ec7a-105">Некоторые управляемые типы невидимы в модели COM, другие видны, но недоступны для создания, однако третьи можно как видеть, так и создавать.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-105">Some managed types are invisible to COM; some are visible but not creatable; and some are both visible and creatable.</span></span> <span data-ttu-id="7ec7a-106">В сборку можно включать типы любого вида в любом сочетании.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-106">An assembly can comprise any combination of invisible, visible, not creatable, and creatable types.</span></span> <span data-ttu-id="7ec7a-107">Для полноты информации определите типы в сборке, которые будут предоставлены модели COM. Особое внимание уделите типам, входящим в подмножество типов, предоставляемых платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-107">For completeness, identify the types in an assembly that you intend to expose to COM, especially when those types are a subset of the types exposed to the .NET Framework.</span></span>

  <span data-ttu-id="7ec7a-108">Дополнительные сведения см. в разделе [Уточнение типов .NET для взаимодействия](qualifying-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="7ec7a-108">For additional information, see [Qualifying .NET Types for Interoperation](qualifying-net-types-for-interoperation.md).</span></span>

- <span data-ttu-id="7ec7a-109">Инструкции по управлению версиями</span><span class="sxs-lookup"><span data-stu-id="7ec7a-109">Versioning instructions</span></span>

  <span data-ttu-id="7ec7a-110">В отношении управления версиями управляемых классов, которые реализуют интерфейс класса (создаваемые в результате COM-взаимодействия класс), действуют определенные ограничения.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-110">Managed classes that implement the class interface (a COM interop-generated interface) are subject to versioning restrictions.</span></span>

  <span data-ttu-id="7ec7a-111">Рекомендации по использованию интерфейса класса см. в разделе [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface) (Введение в интерфейс класса).</span><span class="sxs-lookup"><span data-stu-id="7ec7a-111">For guidelines on using the class interface, see [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface).</span></span>

- <span data-ttu-id="7ec7a-112">Инструкции по развертыванию</span><span class="sxs-lookup"><span data-stu-id="7ec7a-112">Deployment instructions</span></span>

  <span data-ttu-id="7ec7a-113">Сборки со строгими именами, подписанные издателем, могут устанавливаться в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-113">Strong-named assemblies that are signed by a publisher can be installed into the global assembly cache.</span></span> <span data-ttu-id="7ec7a-114">Неподписанные сборки необходимо устанавливать на компьютер пользователя в виде частных сборок.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-114">Unsigned assemblies must be installed on the user's machine as private assemblies.</span></span>

  <span data-ttu-id="7ec7a-115">Дополнительные сведения см. в разделе [Вопросы безопасности сборок](../app-domains/assembly-security-considerations.md).</span><span class="sxs-lookup"><span data-stu-id="7ec7a-115">For additional information, see [Assembly Security Considerations](../app-domains/assembly-security-considerations.md).</span></span>

- <span data-ttu-id="7ec7a-116">Включение библиотеки типов</span><span class="sxs-lookup"><span data-stu-id="7ec7a-116">Type library inclusion</span></span>

  <span data-ttu-id="7ec7a-117">Для использования большинства типов в COM-приложении требуется библиотека типов.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-117">Most types require a type library when consumed by a COM application.</span></span> <span data-ttu-id="7ec7a-118">Вы можете создать библиотеку типов самостоятельно или поручить эту задачу разработчикам COM-приложений.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-118">You can generate a type library or have COM developers perform this task.</span></span> <span data-ttu-id="7ec7a-119">Пакет средств разработки программного обеспечения (SDK) Windows предоставляет следующие возможности для создания библиотеки типов:</span><span class="sxs-lookup"><span data-stu-id="7ec7a-119">The Windows Software Development Kit (SDK) provides the following options for generating a type library:</span></span>

  - [<span data-ttu-id="7ec7a-120">Программа экспорта библиотек типов</span><span class="sxs-lookup"><span data-stu-id="7ec7a-120">Type Library Exporter</span></span>](#cpconpackagingassemblyforcomanchor1)

  - [<span data-ttu-id="7ec7a-121">Класс TypeLibConverter</span><span class="sxs-lookup"><span data-stu-id="7ec7a-121">TypeLibConverter Class</span></span>](#cpconpackagingassemblyforcomanchor2)

  - [<span data-ttu-id="7ec7a-122">Средство регистрации сборок</span><span class="sxs-lookup"><span data-stu-id="7ec7a-122">Assembly Registration Tool</span></span>](#cpconpackagingassemblyforcomanchor3)

  - [<span data-ttu-id="7ec7a-123">Средство установки служб .NET</span><span class="sxs-lookup"><span data-stu-id="7ec7a-123">.NET Services Installation Tool</span></span>](#cpconpackagingassemblyforcomanchor4)

  <span data-ttu-id="7ec7a-124">Независимо от выбранного механизма, в созданную библиотеку типов включаются только открытые типы, определенные в предоставленной сборке.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-124">Regardless of the mechanism you choose, only public types defined in the assembly you supply are included in the generated type library.</span></span>

  <span data-ttu-id="7ec7a-125">Библиотеку типов можно упаковать в отдельный файл или внедрить в виде файла ресурсов Win32 в приложение на основе платформе .NET.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-125">You can package a type library as a separate file or embed it as Win32 resource file within a .NET-based application.</span></span> <span data-ttu-id="7ec7a-126">В Microsoft Visual Basic 6.0 эта задача выполняется автоматически, однако при использовании [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] внедрение библиотеки типов осуществляется вручную.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-126">Microsoft Visual Basic 6.0 performed this task for you automatically; however, when using [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)], you must embed your type library manually.</span></span> <span data-ttu-id="7ec7a-127">Инструкции см. в разделе [Практическое руководство. Встраивание библиотек типов как ресурсов Win32 в приложения на основе платформы .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7ec7a-127">For instructions, see [How to: Embed Type Libraries as Win32 Resources in .NET-Based Applications](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span></span>

<a name="cpconpackagingassemblyforcomanchor1"></a>

## <a name="type-library-exporter"></a><span data-ttu-id="7ec7a-128">программа экспорта библиотек типов</span><span class="sxs-lookup"><span data-stu-id="7ec7a-128">Type Library Exporter</span></span>

<span data-ttu-id="7ec7a-129">[Программа экспорта библиотек типов (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) — это средство командной строки, которое преобразует классы и интерфейсы, содержащиеся в сборке, в библиотеку типов COM.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-129">The [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) is a command-line tool that converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="7ec7a-130">После получения информации о типе класса COM-клиенты могут создать экземпляр класса .NET и вызывать его методы так, как если бы он был COM-объектом.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-130">Once the type information of the class is available, COM clients can create an instance of the .NET class and call the methods of the instance, just as if it were a COM object.</span></span> <span data-ttu-id="7ec7a-131">Программа Tlbexp.exe преобразует всю сборку за одну операцию.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-131">Tlbexp.exe converts an entire assembly at one time.</span></span> <span data-ttu-id="7ec7a-132">Программу Tlbexp.exe нельзя использовать с целью генерации сведений о типах для подмножества типов, определенных в сборке.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-132">You cannot use Tlbexp.exe to generate type information for a subset of the types defined in an assembly.</span></span>

<a name="cpconpackagingassemblyforcomanchor2"></a>

## <a name="typelibconverter-class"></a><span data-ttu-id="7ec7a-133">Класс TypeLibConverter</span><span class="sxs-lookup"><span data-stu-id="7ec7a-133">TypeLibConverter Class</span></span>

<span data-ttu-id="7ec7a-134">Класс <xref:System.Runtime.InteropServices.TypeLibConverter> располагается в пространстве имен **System.Runtime.Interop** и преобразует классы и интерфейсы, содержащиеся в сборке, в библиотеку типов COM.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-134">The <xref:System.Runtime.InteropServices.TypeLibConverter> class, located in the **System.Runtime.Interop** namespace, converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="7ec7a-135">Этот API предоставляет те же сведения, что и программа экспорта библиотек типов, которая описывается в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-135">This API produces the same type information as the Type Library Exporter, described in the previous section.</span></span>

<span data-ttu-id="7ec7a-136">Класс **TypeLibConverter** реализует <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-136">The **TypeLibConverter class** implements the <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span></span>

<a name="cpconpackagingassemblyforcomanchor3"></a>

## <a name="assembly-registration-tool"></a><span data-ttu-id="7ec7a-137">Средство регистрации сборок</span><span class="sxs-lookup"><span data-stu-id="7ec7a-137">Assembly Registration Tool</span></span>

<span data-ttu-id="7ec7a-138">[Средство регистрации сборок (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) позволяет создавать и регистрировать библиотеку типов с использованием параметров **/tlb:** .</span><span class="sxs-lookup"><span data-stu-id="7ec7a-138">The [Assembly Registration Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) can generate and register a type library when you apply the **/tlb:** option.</span></span> <span data-ttu-id="7ec7a-139">COM-клиентам требуется установка библиотек типов в реестр Windows.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-139">COM clients require that type libraries be installed in the Windows registry.</span></span> <span data-ttu-id="7ec7a-140">Без этого параметра программа Regasm.exe регистрирует только типы в сборке, а не библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-140">Without this option, Regasm.exe only registers the types in an assembly, not the type library.</span></span> <span data-ttu-id="7ec7a-141">Регистрация типов сборки и регистрация библиотеки типов — это разные операции.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-141">Registering the types in an assembly and registering the type library are distinct activities.</span></span>

<a name="cpconpackagingassemblyforcomanchor4"></a>

## <a name="net-services-installation-tool"></a><span data-ttu-id="7ec7a-142">Средство установки служб .NET</span><span class="sxs-lookup"><span data-stu-id="7ec7a-142">.NET Services Installation Tool</span></span>

<span data-ttu-id="7ec7a-143">[Средство установки служб .NET (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) добавляет управляемые классы в службы компонентов Windows 2000 и реализует одновременно несколько задач.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-143">The [.NET Services Installation Tool (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) adds managed classes to Windows 2000 Component Services and combines several tasks within a single tool.</span></span> <span data-ttu-id="7ec7a-144">Помимо загрузки и регистрации сборки программа Regsvcs.exe может создавать, регистрировать и устанавливать библиотеку типов в существующее приложение COM+ 1.0.</span><span class="sxs-lookup"><span data-stu-id="7ec7a-144">In addition to loading and registering an assembly, Regsvcs.exe can generate, register, and install the type library into an existing COM+ 1.0 application.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ec7a-145">См. также</span><span class="sxs-lookup"><span data-stu-id="7ec7a-145">See also</span></span>

- <xref:System.Runtime.InteropServices.TypeLibConverter>
- <xref:System.Runtime.InteropServices.ITypeLibConverter>
- [<span data-ttu-id="7ec7a-146">Предоставление компонентов .NET Framework клиентам COM</span><span class="sxs-lookup"><span data-stu-id="7ec7a-146">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="7ec7a-147">Oпределение типов .NET для взаимодействия</span><span class="sxs-lookup"><span data-stu-id="7ec7a-147">Qualifying .NET Types for Interoperation</span></span>](qualifying-net-types-for-interoperation.md)
- <span data-ttu-id="7ec7a-148">[Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface) (Введение в интерфейс класса)</span><span class="sxs-lookup"><span data-stu-id="7ec7a-148">[Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface)</span></span>
- [<span data-ttu-id="7ec7a-149">Вопросы безопасности сборок</span><span class="sxs-lookup"><span data-stu-id="7ec7a-149">Assembly Security Considerations</span></span>](../app-domains/assembly-security-considerations.md)
- [<span data-ttu-id="7ec7a-150">Tlbexp.exe (программа экспорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="7ec7a-150">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="7ec7a-151">Регистрация сборок в COM</span><span class="sxs-lookup"><span data-stu-id="7ec7a-151">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="7ec7a-152">[Практическое руководство. Встраивание библиотек типов как ресурсов Win32 в приложения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7ec7a-152">[How to: Embed Type Libraries as Win32 Resources in Applications](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))</span></span>
