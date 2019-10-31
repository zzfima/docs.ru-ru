---
title: Практическое руководство. Создание ссылки на типы .NET из COM
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
ms.openlocfilehash: 0223cb25b933cc84af49aa86d90259fdf1fd3efc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124177"
---
# <a name="how-to-reference-net-types-from-com"></a><span data-ttu-id="23617-102">Практическое руководство. Создание ссылки на типы .NET из COM</span><span class="sxs-lookup"><span data-stu-id="23617-102">How to: Reference .NET Types from COM</span></span>
<span data-ttu-id="23617-103">С точки зрения кода клиента и сервера различия между COM и .NET Framework практически незаметны.</span><span class="sxs-lookup"><span data-stu-id="23617-103">From the point of view of client and server code, the differences between COM and the .NET Framework are largely invisible.</span></span> <span data-ttu-id="23617-104">Клиенты Microsoft Visual Basic могут просматривать объект .NET в обозревателе объектов, который позволяет просмотреть методы, синтаксис, свойства и поля объекта точно так же, как если бы это был объект COM.</span><span class="sxs-lookup"><span data-stu-id="23617-104">Microsoft Visual Basic clients can view a .NET object in the object browser, which exposes the object methods and syntax, properties, and fields exactly as if it were any other COM object.</span></span>  
  
 <span data-ttu-id="23617-105">Процесс импорта библиотеки типов для клиентов C++ несколько сложнее, хотя для экспорта метаданных в библиотеку типов COM можно использовать те же средства.</span><span class="sxs-lookup"><span data-stu-id="23617-105">The process for importing a type library is slightly more complicated for C++ clients, although you use the same tools to export metadata to a COM type library.</span></span> <span data-ttu-id="23617-106">Чтобы получить доступ к элементам объекта .NET из неуправляемого клиента C++, укажите ссылку на TLB-файл (файл, созданный с помощью программы Tlbexp.exe) в директиве **#import**.</span><span class="sxs-lookup"><span data-stu-id="23617-106">To reference .NET object members from an unmanaged C++ client, reference the TLB file (produced with Tlbexp.exe) with the **#import** directive.</span></span> <span data-ttu-id="23617-107">При указании ссылки на библиотеку типов из C++ необходимо указать параметр **raw_interfaces_only** или импортировать определения из библиотеки базовых классов Mscorlib.tlb.</span><span class="sxs-lookup"><span data-stu-id="23617-107">When referencing a type library from C++, you must either specify the **raw_interfaces_only** option or import the definitions in the base class library, Mscorlib.tlb.</span></span>  
  
### <a name="to-import-a-library"></a><span data-ttu-id="23617-108">Импорт библиотеки</span><span class="sxs-lookup"><span data-stu-id="23617-108">To import a library</span></span>  
  
- <span data-ttu-id="23617-109">Укажите параметр **raw_interfaces_only** в диалоговом окне директивы **#import**.</span><span class="sxs-lookup"><span data-stu-id="23617-109">Specify the **raw_interfaces_only** option in the **#import** directive.</span></span> <span data-ttu-id="23617-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="23617-110">For example:</span></span>  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     <span data-ttu-id="23617-111">\- или -</span><span class="sxs-lookup"><span data-stu-id="23617-111">-or-</span></span>  
  
- <span data-ttu-id="23617-112">Включите директиву #import для Mscorlib.tlb.</span><span class="sxs-lookup"><span data-stu-id="23617-112">Include an #import directive for Mscorlib.tlb.</span></span> <span data-ttu-id="23617-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="23617-113">For example:</span></span>  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="23617-114">См. также</span><span class="sxs-lookup"><span data-stu-id="23617-114">See also</span></span>

- [<span data-ttu-id="23617-115">Предоставление компонентов .NET Framework клиентам COM</span><span class="sxs-lookup"><span data-stu-id="23617-115">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="23617-116">Регистрация сборок в COM</span><span class="sxs-lookup"><span data-stu-id="23617-116">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="23617-117">[Вызов объекта .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="23617-117">[Calling a .NET Object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span></span>
- <span data-ttu-id="23617-118">[Развертывание приложения для доступа к COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="23617-118">[Deploying an Application for COM Access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span></span>
