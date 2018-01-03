---
title: "Практическое руководство. Создание ссылки на типы .NET из COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c6427254aeec1a9e272579665fcd9893daa2316
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-reference-net-types-from-com"></a><span data-ttu-id="f8fb9-102">Практическое руководство. Создание ссылки на типы .NET из COM</span><span class="sxs-lookup"><span data-stu-id="f8fb9-102">How to: Reference .NET Types from COM</span></span>
<span data-ttu-id="f8fb9-103">С точки зрения кода клиента и сервера различия между COM и .NET Framework практически незаметны.</span><span class="sxs-lookup"><span data-stu-id="f8fb9-103">From the point of view of client and server code, the differences between COM and the .NET Framework are largely invisible.</span></span> <span data-ttu-id="f8fb9-104">Клиенты Microsoft Visual Basic могут просматривать объект .NET в обозревателе объектов, который позволяет просмотреть методы, синтаксис, свойства и поля объекта точно так же, как если бы это был объект COM.</span><span class="sxs-lookup"><span data-stu-id="f8fb9-104">Microsoft Visual Basic clients can view a .NET object in the object browser, which exposes the object methods and syntax, properties, and fields exactly as if it were any other COM object.</span></span>  
  
 <span data-ttu-id="f8fb9-105">Процесс импорта библиотеки типов для клиентов C++ несколько сложнее, хотя для экспорта метаданных в библиотеку типов COM можно использовать те же средства.</span><span class="sxs-lookup"><span data-stu-id="f8fb9-105">The process for importing a type library is slightly more complicated for C++ clients, although you use the same tools to export metadata to a COM type library.</span></span> <span data-ttu-id="f8fb9-106">Чтобы получить доступ к элементам объекта .NET из неуправляемого клиента C++, укажите ссылку на TLB-файл (файл, созданный с помощью программы Tlbexp.exe) в директиве **#import**.</span><span class="sxs-lookup"><span data-stu-id="f8fb9-106">To reference .NET object members from an unmanaged C++ client, reference the TLB file (produced with Tlbexp.exe) with the **#import** directive.</span></span> <span data-ttu-id="f8fb9-107">При указании ссылки на библиотеку типов из C++ необходимо указать параметр **raw_interfaces_only** или импортировать определения из библиотеки базовых классов Mscorlib.tlb.</span><span class="sxs-lookup"><span data-stu-id="f8fb9-107">When referencing a type library from C++, you must either specify the **raw_interfaces_only** option or import the definitions in the base class library, Mscorlib.tlb.</span></span>  
  
### <a name="to-import-a-library"></a><span data-ttu-id="f8fb9-108">Импорт библиотеки</span><span class="sxs-lookup"><span data-stu-id="f8fb9-108">To import a library</span></span>  
  
-   <span data-ttu-id="f8fb9-109">Укажите параметр **raw_interfaces_only** в диалоговом окне директивы **#import**.</span><span class="sxs-lookup"><span data-stu-id="f8fb9-109">Specify the **raw_interfaces_only** option in the **#import** directive.</span></span> <span data-ttu-id="f8fb9-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="f8fb9-110">For example:</span></span>  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     <span data-ttu-id="f8fb9-111">-или-</span><span class="sxs-lookup"><span data-stu-id="f8fb9-111">-or-</span></span>  
  
-   <span data-ttu-id="f8fb9-112">Включите директиву #import для Mscorlib.tlb.</span><span class="sxs-lookup"><span data-stu-id="f8fb9-112">Include an #import directive for Mscorlib.tlb.</span></span> <span data-ttu-id="f8fb9-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="f8fb9-113">For example:</span></span>  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f8fb9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f8fb9-114">See Also</span></span>  
 [<span data-ttu-id="f8fb9-115">Предоставление компонентов .NET Framework клиентам COM</span><span class="sxs-lookup"><span data-stu-id="f8fb9-115">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="f8fb9-116">Регистрация сборок в COM</span><span class="sxs-lookup"><span data-stu-id="f8fb9-116">Registering Assemblies with COM</span></span>](../../../docs/framework/interop/registering-assemblies-with-com.md)  
 [<span data-ttu-id="f8fb9-117">Вызов объекта .NET</span><span class="sxs-lookup"><span data-stu-id="f8fb9-117">Calling a .NET Object</span></span>](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33)  
 [<span data-ttu-id="f8fb9-118">Развертывание приложения для доступа к COM</span><span class="sxs-lookup"><span data-stu-id="f8fb9-118">Deploying an Application for COM Access</span></span>](http://msdn.microsoft.com/en-us/fb63564c-c1b9-4655-a094-a235625882ce)
