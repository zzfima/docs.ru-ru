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
ms.openlocfilehash: cb45fc253e24c9770436432d2734ba8fce249453
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662372"
---
# <a name="packaging-an-assembly-for-com"></a><span data-ttu-id="e5449-102">Упаковка сборки для модели COM</span><span class="sxs-lookup"><span data-stu-id="e5449-102">Packaging an Assembly for COM</span></span>

<span data-ttu-id="e5449-103">Разработчики приложений на основе модели COM могут использовать следующую информацию об управляемых типах, которые они планируют включать в свои приложения:</span><span class="sxs-lookup"><span data-stu-id="e5449-103">COM developers can benefit from the following information about the managed types they plan to incorporate in their application:</span></span>

- <span data-ttu-id="e5449-104">Список типов, которые можно использовать в приложениях на основе модели COM</span><span class="sxs-lookup"><span data-stu-id="e5449-104">A list of types that COM applications can consume</span></span>

  <span data-ttu-id="e5449-105">Некоторые управляемые типы невидимы в модели COM, другие видны, но недоступны для создания, однако третьи можно как видеть, так и создавать.</span><span class="sxs-lookup"><span data-stu-id="e5449-105">Some managed types are invisible to COM; some are visible but not creatable; and some are both visible and creatable.</span></span> <span data-ttu-id="e5449-106">В сборку можно включать типы любого вида в любом сочетании.</span><span class="sxs-lookup"><span data-stu-id="e5449-106">An assembly can comprise any combination of invisible, visible, not creatable, and creatable types.</span></span> <span data-ttu-id="e5449-107">Для полноты информации определите типы в сборке, которые будут предоставлены модели COM. Особое внимание уделите типам, входящим в подмножество типов, предоставляемых платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e5449-107">For completeness, identify the types in an assembly that you intend to expose to COM, especially when those types are a subset of the types exposed to the .NET Framework.</span></span>

  <span data-ttu-id="e5449-108">Дополнительные сведения см. в разделе [Уточнение типов .NET для взаимодействия](qualifying-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="e5449-108">For additional information, see [Qualifying .NET Types for Interoperation](qualifying-net-types-for-interoperation.md).</span></span>

- <span data-ttu-id="e5449-109">Инструкции по управлению версиями</span><span class="sxs-lookup"><span data-stu-id="e5449-109">Versioning instructions</span></span>

  <span data-ttu-id="e5449-110">В отношении управления версиями управляемых классов, которые реализуют интерфейс класса (создаваемые в результате COM-взаимодействия класс), действуют определенные ограничения.</span><span class="sxs-lookup"><span data-stu-id="e5449-110">Managed classes that implement the class interface (a COM interop-generated interface) are subject to versioning restrictions.</span></span>

  <span data-ttu-id="e5449-111">Рекомендации по использованию интерфейса класса см. в разделе [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface) (Введение в интерфейс класса).</span><span class="sxs-lookup"><span data-stu-id="e5449-111">For guidelines on using the class interface, see [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface).</span></span>

- <span data-ttu-id="e5449-112">Инструкции по развертыванию</span><span class="sxs-lookup"><span data-stu-id="e5449-112">Deployment instructions</span></span>

  <span data-ttu-id="e5449-113">Сборки со строгими именами, подписанные издателем, могут устанавливаться в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="e5449-113">Strong-named assemblies that are signed by a publisher can be installed into the global assembly cache.</span></span> <span data-ttu-id="e5449-114">Неподписанные сборки необходимо устанавливать на компьютер пользователя в виде частных сборок.</span><span class="sxs-lookup"><span data-stu-id="e5449-114">Unsigned assemblies must be installed on the user's machine as private assemblies.</span></span>

  <span data-ttu-id="e5449-115">Дополнительные сведения см. в разделе [Вопросы безопасности сборок](../app-domains/assembly-security-considerations.md).</span><span class="sxs-lookup"><span data-stu-id="e5449-115">For additional information, see [Assembly Security Considerations](../app-domains/assembly-security-considerations.md).</span></span>

- <span data-ttu-id="e5449-116">Включение библиотеки типов</span><span class="sxs-lookup"><span data-stu-id="e5449-116">Type library inclusion</span></span>

  <span data-ttu-id="e5449-117">Для использования большинства типов в COM-приложении требуется библиотека типов.</span><span class="sxs-lookup"><span data-stu-id="e5449-117">Most types require a type library when consumed by a COM application.</span></span> <span data-ttu-id="e5449-118">Вы можете создать библиотеку типов самостоятельно или поручить эту задачу разработчикам COM-приложений.</span><span class="sxs-lookup"><span data-stu-id="e5449-118">You can generate a type library or have COM developers perform this task.</span></span> <span data-ttu-id="e5449-119">Пакет средств разработки программного обеспечения (SDK) Windows предоставляет следующие возможности для создания библиотеки типов:</span><span class="sxs-lookup"><span data-stu-id="e5449-119">The Windows Software Development Kit (SDK) provides the following options for generating a type library:</span></span>

  - [<span data-ttu-id="e5449-120">Программа экспорта библиотек типов</span><span class="sxs-lookup"><span data-stu-id="e5449-120">Type Library Exporter</span></span>](#cpconpackagingassemblyforcomanchor1)

  - [<span data-ttu-id="e5449-121">Класс TypeLibConverter</span><span class="sxs-lookup"><span data-stu-id="e5449-121">TypeLibConverter Class</span></span>](#cpconpackagingassemblyforcomanchor2)

  - [<span data-ttu-id="e5449-122">Средство регистрации сборок</span><span class="sxs-lookup"><span data-stu-id="e5449-122">Assembly Registration Tool</span></span>](#cpconpackagingassemblyforcomanchor3)

  - [<span data-ttu-id="e5449-123">Средство установки служб .NET</span><span class="sxs-lookup"><span data-stu-id="e5449-123">.NET Services Installation Tool</span></span>](#cpconpackagingassemblyforcomanchor4)

  <span data-ttu-id="e5449-124">Независимо от выбранного механизма, в созданную библиотеку типов включаются только открытые типы, определенные в предоставленной сборке.</span><span class="sxs-lookup"><span data-stu-id="e5449-124">Regardless of the mechanism you choose, only public types defined in the assembly you supply are included in the generated type library.</span></span>

<span data-ttu-id="e5449-125">Инструкции см. в разделе [Практическое руководство. Встраивание библиотек типов как ресурсов Win32 в приложения на основе платформы .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e5449-125">For instructions, see [How to: Embed Type Libraries as Win32 Resources in .NET-Based Applications](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span></span>

<a name="cpconpackagingassemblyforcomanchor1"></a>

## <a name="type-library-exporter"></a><span data-ttu-id="e5449-126">программа экспорта библиотек типов</span><span class="sxs-lookup"><span data-stu-id="e5449-126">Type Library Exporter</span></span>

<span data-ttu-id="e5449-127">[Программа экспорта библиотек типов (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) — это средство командной строки, которое преобразует классы и интерфейсы, содержащиеся в сборке, в библиотеку типов COM.</span><span class="sxs-lookup"><span data-stu-id="e5449-127">The [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) is a command-line tool that converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="e5449-128">После получения информации о типе класса COM-клиенты могут создать экземпляр класса .NET и вызывать его методы так, как если бы он был COM-объектом.</span><span class="sxs-lookup"><span data-stu-id="e5449-128">Once the type information of the class is available, COM clients can create an instance of the .NET class and call the methods of the instance, just as if it were a COM object.</span></span> <span data-ttu-id="e5449-129">Программа Tlbexp.exe преобразует всю сборку за одну операцию.</span><span class="sxs-lookup"><span data-stu-id="e5449-129">Tlbexp.exe converts an entire assembly at one time.</span></span> <span data-ttu-id="e5449-130">Программу Tlbexp.exe нельзя использовать с целью генерации сведений о типах для подмножества типов, определенных в сборке.</span><span class="sxs-lookup"><span data-stu-id="e5449-130">You cannot use Tlbexp.exe to generate type information for a subset of the types defined in an assembly.</span></span>

<a name="cpconpackagingassemblyforcomanchor2"></a>

## <a name="typelibconverter-class"></a><span data-ttu-id="e5449-131">Класс TypeLibConverter</span><span class="sxs-lookup"><span data-stu-id="e5449-131">TypeLibConverter Class</span></span>

<span data-ttu-id="e5449-132">Класс <xref:System.Runtime.InteropServices.TypeLibConverter> располагается в пространстве имен **System.Runtime.Interop** и преобразует классы и интерфейсы, содержащиеся в сборке, в библиотеку типов COM.</span><span class="sxs-lookup"><span data-stu-id="e5449-132">The <xref:System.Runtime.InteropServices.TypeLibConverter> class, located in the **System.Runtime.Interop** namespace, converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="e5449-133">Этот API предоставляет те же сведения, что и программа экспорта библиотек типов, которая описывается в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="e5449-133">This API produces the same type information as the Type Library Exporter, described in the previous section.</span></span>

<span data-ttu-id="e5449-134">Класс **TypeLibConverter** реализует <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span><span class="sxs-lookup"><span data-stu-id="e5449-134">The **TypeLibConverter class** implements the <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span></span>

<a name="cpconpackagingassemblyforcomanchor3"></a>

## <a name="assembly-registration-tool"></a><span data-ttu-id="e5449-135">Средство регистрации сборок</span><span class="sxs-lookup"><span data-stu-id="e5449-135">Assembly Registration Tool</span></span>

<span data-ttu-id="e5449-136">[Средство регистрации сборок (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) позволяет создавать и регистрировать библиотеку типов с использованием параметров **/tlb:** .</span><span class="sxs-lookup"><span data-stu-id="e5449-136">The [Assembly Registration Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) can generate and register a type library when you apply the **/tlb:** option.</span></span> <span data-ttu-id="e5449-137">COM-клиентам требуется установка библиотек типов в реестр Windows.</span><span class="sxs-lookup"><span data-stu-id="e5449-137">COM clients require that type libraries be installed in the Windows registry.</span></span> <span data-ttu-id="e5449-138">Без этого параметра программа Regasm.exe регистрирует только типы в сборке, а не библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="e5449-138">Without this option, Regasm.exe only registers the types in an assembly, not the type library.</span></span> <span data-ttu-id="e5449-139">Регистрация типов сборки и регистрация библиотеки типов — это разные операции.</span><span class="sxs-lookup"><span data-stu-id="e5449-139">Registering the types in an assembly and registering the type library are distinct activities.</span></span>

<a name="cpconpackagingassemblyforcomanchor4"></a>

## <a name="net-services-installation-tool"></a><span data-ttu-id="e5449-140">Средство установки служб .NET</span><span class="sxs-lookup"><span data-stu-id="e5449-140">.NET Services Installation Tool</span></span>

<span data-ttu-id="e5449-141">[Средство установки служб .NET (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) добавляет управляемые классы в службы компонентов Windows 2000 и реализует одновременно несколько задач.</span><span class="sxs-lookup"><span data-stu-id="e5449-141">The [.NET Services Installation Tool (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) adds managed classes to Windows 2000 Component Services and combines several tasks within a single tool.</span></span> <span data-ttu-id="e5449-142">Помимо загрузки и регистрации сборки программа Regsvcs.exe может создавать, регистрировать и устанавливать библиотеку типов в существующее приложение COM+ 1.0.</span><span class="sxs-lookup"><span data-stu-id="e5449-142">In addition to loading and registering an assembly, Regsvcs.exe can generate, register, and install the type library into an existing COM+ 1.0 application.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5449-143">См. также</span><span class="sxs-lookup"><span data-stu-id="e5449-143">See also</span></span>

- <xref:System.Runtime.InteropServices.TypeLibConverter>
- <xref:System.Runtime.InteropServices.ITypeLibConverter>
- [<span data-ttu-id="e5449-144">Предоставление компонентов .NET Framework клиентам COM</span><span class="sxs-lookup"><span data-stu-id="e5449-144">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="e5449-145">Oпределение типов .NET для взаимодействия</span><span class="sxs-lookup"><span data-stu-id="e5449-145">Qualifying .NET Types for Interoperation</span></span>](qualifying-net-types-for-interoperation.md)
- <span data-ttu-id="e5449-146">[Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface) (Введение в интерфейс класса)</span><span class="sxs-lookup"><span data-stu-id="e5449-146">[Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface)</span></span>
- [<span data-ttu-id="e5449-147">Вопросы безопасности сборок</span><span class="sxs-lookup"><span data-stu-id="e5449-147">Assembly Security Considerations</span></span>](../app-domains/assembly-security-considerations.md)
- [<span data-ttu-id="e5449-148">Tlbexp.exe (программа экспорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="e5449-148">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="e5449-149">Регистрация сборок в COM</span><span class="sxs-lookup"><span data-stu-id="e5449-149">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="e5449-150">[Практическое руководство. Встраивание библиотек типов как ресурсов Win32 в приложения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e5449-150">[How to: Embed Type Libraries as Win32 Resources in Applications](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))</span></span>
