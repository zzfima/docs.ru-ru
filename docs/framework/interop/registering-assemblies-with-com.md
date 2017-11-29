---
title: "Регистрация сборок в COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, registering assemblies
- unregistering assemblies
- interoperation with unmanaged code, registering assemblies
- registering assemblies
ms.assetid: 87925795-a3ae-4833-b138-125413478551
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c04511772e83129be8042ba5758dc647f82243c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="registering-assemblies-with-com"></a><span data-ttu-id="a504a-102">Регистрация сборок в COM</span><span class="sxs-lookup"><span data-stu-id="a504a-102">Registering Assemblies with COM</span></span>
<span data-ttu-id="a504a-103">С помощью программы командной строки, которая называется [средством регистрации сборок (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md), можно регистрировать сборки для использования с моделью COM и отменять их регистрацию.</span><span class="sxs-lookup"><span data-stu-id="a504a-103">You can run a command-line tool called the [Assembly Registration Tool (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) to register or unregister an assembly for use with COM.</span></span> <span data-ttu-id="a504a-104">Программа Regasm.exe добавляет сведения о классе в системный реестр, что обеспечивает прозрачное использование класса .NET Framework COM-клиентами.</span><span class="sxs-lookup"><span data-stu-id="a504a-104">Regasm.exe adds information about the class to the system registry so COM clients can use the .NET Framework class transparently.</span></span> <span data-ttu-id="a504a-105">Класс <xref:System.Runtime.InteropServices.RegistrationServices> реализует эквивалентные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="a504a-105">The <xref:System.Runtime.InteropServices.RegistrationServices> class provides the equivalent functionality.</span></span>  
  
 <span data-ttu-id="a504a-106">Управляемый компонент необходимо регистрировать в реестре Windows до того, как он будет активироваться из COM-клиента.</span><span class="sxs-lookup"><span data-stu-id="a504a-106">A managed component must be registered in the Windows registry before it can be activated from a COM client.</span></span> <span data-ttu-id="a504a-107">В следующей таблице показаны разделы, которые программа Regasm.exe обычно добавляет в реестр Windows.</span><span class="sxs-lookup"><span data-stu-id="a504a-107">The following table shows the keys that Regasm.exe typically adds to the Windows registry.</span></span> <span data-ttu-id="a504a-108">(000000 указывает фактическое значение GUID.)</span><span class="sxs-lookup"><span data-stu-id="a504a-108">(000000 indicates the actual GUID value.)</span></span>  
  
|<span data-ttu-id="a504a-109">GUID</span><span class="sxs-lookup"><span data-stu-id="a504a-109">GUID</span></span>|<span data-ttu-id="a504a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a504a-110">Description</span></span>|<span data-ttu-id="a504a-111">Раздел реестра</span><span class="sxs-lookup"><span data-stu-id="a504a-111">Registry key</span></span>|  
|----------|-----------------|------------------|  
|<span data-ttu-id="a504a-112">CLSID</span><span class="sxs-lookup"><span data-stu-id="a504a-112">CLSID</span></span>|<span data-ttu-id="a504a-113">Идентификатор класса</span><span class="sxs-lookup"><span data-stu-id="a504a-113">Class identifier</span></span>|<span data-ttu-id="a504a-114">HKEY_CLASSES_ROOT\CLSID\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="a504a-114">HKEY_CLASSES_ROOT\CLSID\\{000…000}</span></span>|  
|<span data-ttu-id="a504a-115">IID</span><span class="sxs-lookup"><span data-stu-id="a504a-115">IID</span></span>|<span data-ttu-id="a504a-116">Идентификатор интерфейса</span><span class="sxs-lookup"><span data-stu-id="a504a-116">Interface identifier</span></span>|<span data-ttu-id="a504a-117">HKEY_CLASSES_ROOT\Interface\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="a504a-117">HKEY_CLASSES_ROOT\Interface\\{000…000}</span></span>|  
|<span data-ttu-id="a504a-118">LIBID</span><span class="sxs-lookup"><span data-stu-id="a504a-118">LIBID</span></span>|<span data-ttu-id="a504a-119">Идентификатор библиотеки</span><span class="sxs-lookup"><span data-stu-id="a504a-119">Library identifier</span></span>|<span data-ttu-id="a504a-120">HKEY_CLASSES_ROOT\TypeLib\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="a504a-120">HKEY_CLASSES_ROOT\TypeLib\\{000…000}</span></span>|  
|<span data-ttu-id="a504a-121">ProgID</span><span class="sxs-lookup"><span data-stu-id="a504a-121">ProgID</span></span>|<span data-ttu-id="a504a-122">Программный идентификатор</span><span class="sxs-lookup"><span data-stu-id="a504a-122">Programmatic identifier</span></span>|<span data-ttu-id="a504a-123">HKEY_CLASSES_ROOT\000…000</span><span class="sxs-lookup"><span data-stu-id="a504a-123">HKEY_CLASSES_ROOT\000…000</span></span>|  
  
 <span data-ttu-id="a504a-124">В разделе HKCR\CLSID\\{0000…0000} в качестве значения по умолчанию устанавливается идентификатор ProgID класса, а также добавляются два именованных значения (Class и Assembly).</span><span class="sxs-lookup"><span data-stu-id="a504a-124">Under the HKCR\CLSID\\{0000…0000} key, the default value is set to the ProgID of the class, and two new named values, Class and Assembly, are added.</span></span> <span data-ttu-id="a504a-125">Среда выполнения считывает Assembly из реестра и передает его в средство определения сборок среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a504a-125">The runtime reads the Assembly value from the registry and passes it on to the runtime assembly resolver.</span></span> <span data-ttu-id="a504a-126">Средство определения сборок пытается найти сборку по таким сведениям о ней, как имя и номер версии.</span><span class="sxs-lookup"><span data-stu-id="a504a-126">The assembly resolver attempts to locate the assembly, based on assembly information such as the name and version number.</span></span> <span data-ttu-id="a504a-127">Средство определения сборок может находить сборки в следующих расположениях:</span><span class="sxs-lookup"><span data-stu-id="a504a-127">For the assembly resolver to locate an assembly, the assembly has to be in one of the following locations:</span></span>  
  
-   <span data-ttu-id="a504a-128">Глобальный кэш сборок (для сборок со строгим именем).</span><span class="sxs-lookup"><span data-stu-id="a504a-128">The global assembly cache (must be a strong-named assembly).</span></span>  
  
-   <span data-ttu-id="a504a-129">В каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="a504a-129">In the application directory.</span></span> <span data-ttu-id="a504a-130">Сборки, загруженные по пути приложения, доступны только из этого приложения.</span><span class="sxs-lookup"><span data-stu-id="a504a-130">Assemblies loaded from the application path are only accessible from that application.</span></span>  
  
-   <span data-ttu-id="a504a-131">По пути к файлу, указанному в параметре **/codebase** программы Regasm.exe.</span><span class="sxs-lookup"><span data-stu-id="a504a-131">Along an file path specified with the **/codebase** option to Regasm.exe.</span></span>  
  
 <span data-ttu-id="a504a-132">Программа Regasm.exe также создает подраздел InProcServer32 в разделе HKCR\CLSID\\{0000…0000}.</span><span class="sxs-lookup"><span data-stu-id="a504a-132">Regasm.exe also creates the InProcServer32 key under the HKCR\CLSID\\{0000…0000} key.</span></span> <span data-ttu-id="a504a-133">В качестве значения по умолчанию этому разделу присваивается имя библиотеки DLL, которая инициализирует общеязыковую среду выполнения (Mscoree.dll).</span><span class="sxs-lookup"><span data-stu-id="a504a-133">The default value for the key is set to the name of the DLL that initializes the common language runtime (Mscoree.dll).</span></span>  
  
## <a name="examining-registry-entries"></a><span data-ttu-id="a504a-134">Проверка записей реестра</span><span class="sxs-lookup"><span data-stu-id="a504a-134">Examining Registry Entries</span></span>  
 <span data-ttu-id="a504a-135">COM-взаимодействие предоставляет стандартную реализацию фабрики класса для создания экземпляра любого класса .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a504a-135">COM interop provides a standard class factory implementation to create an instance of any .NET Framework class.</span></span> <span data-ttu-id="a504a-136">Клиенты могут вызывать **DllGetClassObject** для управляемой библиотеки DLL, чтобы получить фабрику класса и создать объекты так же, как и для любого другого COM-компонента.</span><span class="sxs-lookup"><span data-stu-id="a504a-136">Clients can call **DllGetClassObject** on the managed DLL to get a class factory and create objects, just as they would with any other COM component.</span></span>  
  
 <span data-ttu-id="a504a-137">В подразделе `InprocServer32` вместо традиционной библиотеки типов COM указывается ссылка на библиотеку Mscoree.dll. Это указывает на то, что общеязыковая среда выполнения создает объект.</span><span class="sxs-lookup"><span data-stu-id="a504a-137">For the `InprocServer32` subkey, a reference to Mscoree.dll appears in place of a traditional COM type library to indicate that the common language runtime creates the managed object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a504a-138">См. также</span><span class="sxs-lookup"><span data-stu-id="a504a-138">See Also</span></span>  
 [<span data-ttu-id="a504a-139">Предоставление компонентов .NET Framework клиентам COM</span><span class="sxs-lookup"><span data-stu-id="a504a-139">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="a504a-140">Практическое руководство. Создание ссылки на типы .NET из COM</span><span class="sxs-lookup"><span data-stu-id="a504a-140">How to: Reference .NET Types from COM</span></span>](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)  
 [<span data-ttu-id="a504a-141">Вызов объекта .NET</span><span class="sxs-lookup"><span data-stu-id="a504a-141">Calling a .NET Object</span></span>](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33)  
 [<span data-ttu-id="a504a-142">Развертывание приложения для доступа к COM</span><span class="sxs-lookup"><span data-stu-id="a504a-142">Deploying an Application for COM Access</span></span>](http://msdn.microsoft.com/en-us/fb63564c-c1b9-4655-a094-a235625882ce)
