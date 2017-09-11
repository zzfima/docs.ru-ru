---
title: "Взаимодействие (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: df2f33c4599baef6d606738cbe5766fdd88e4ef3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="ca7c8-102">Взаимодействие (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="ca7c8-102">Interoperability (C# Programming Guide)</span></span>
<span data-ttu-id="ca7c8-103">Возможность взаимодействия позволяет использовать уже созданный неуправляемый код, экономя средства на разработку.</span><span class="sxs-lookup"><span data-stu-id="ca7c8-103">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="ca7c8-104">Код, который выполняется под управлением среды CLR, называется *управляемым кодом*, а код, который выполняется вне среды CLR, называется *неуправляемым кодом*.</span><span class="sxs-lookup"><span data-stu-id="ca7c8-104">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="ca7c8-105">COM, COM +, компоненты C++, компоненты ActiveX и Microsoft Win32 API являются примерами неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ca7c8-105">COM, COM+, C++ components, ActiveX components, and Microsoft Win32 API are examples of unmanaged code.</span></span>  
  
 <span data-ttu-id="ca7c8-106">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] обеспечивает взаимодействие с неуправляемым кодом посредством служб вызова неуправляемого кода (PInvoke), пространства имен <xref:System.Runtime.InteropServices>, COM-взаимодействия и взаимодействия с C++.</span><span class="sxs-lookup"><span data-stu-id="ca7c8-106">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca7c8-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="ca7c8-107">In This Section</span></span>  
 [<span data-ttu-id="ca7c8-108">Общие сведения о взаимодействии</span><span class="sxs-lookup"><span data-stu-id="ca7c8-108">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 <span data-ttu-id="ca7c8-109">Описывает способы взаимодействия между управляемым кодом C# и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="ca7c8-109">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="ca7c8-110">Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C# 2010</span><span class="sxs-lookup"><span data-stu-id="ca7c8-110">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="ca7c8-111">Описывает возможности, представленные в Visual C#, которые упрощают программирование для Office.</span><span class="sxs-lookup"><span data-stu-id="ca7c8-111">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="ca7c8-112">Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="ca7c8-112">How to: Use Indexed Properties in COM Interop Programming</span></span>](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="ca7c8-113">Описывает использование индексированных свойств для доступа к свойствам COM, которые имеют параметры.</span><span class="sxs-lookup"><span data-stu-id="ca7c8-113">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="ca7c8-114">Практическое руководство. Использование вызова неуправляемого кода для воспроизведения звукового файла</span><span class="sxs-lookup"><span data-stu-id="ca7c8-114">How to: Use Platform Invoke to Play a Wave File</span></span>](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="ca7c8-115">Описывает, как использовать платформу вызова служб, чтобы воспроизвести звуковой WAV-файл в операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="ca7c8-115">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 <span data-ttu-id="ca7c8-116">[Walkthrough: Office Programming](../../../csharp/programming-guide/interop/walkthrough-office-programming.md) (Пошаговое руководство. Программирование приложений Office)</span><span class="sxs-lookup"><span data-stu-id="ca7c8-116">[Walkthrough: Office Programming](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)</span></span>  
 <span data-ttu-id="ca7c8-117">Описывает процесс создания книги Excel и документа Word со ссылкой на эту книгу.</span><span class="sxs-lookup"><span data-stu-id="ca7c8-117">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="ca7c8-118">Пример COM-класса</span><span class="sxs-lookup"><span data-stu-id="ca7c8-118">Example COM Class</span></span>](../../../csharp/programming-guide/interop/example-com-class.md)  
 <span data-ttu-id="ca7c8-119">Предлагает пример предоставления класса C# в качестве COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="ca7c8-119">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ca7c8-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ca7c8-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ca7c8-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ca7c8-121">See Also</span></span>  
 <span data-ttu-id="ca7c8-122"><xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ca7c8-122"><xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="ca7c8-123">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ca7c8-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ca7c8-124">[Взаимодействие с неуправляемым кодом](https://msdn.microsoft.com/library/sd10k43k) </span><span class="sxs-lookup"><span data-stu-id="ca7c8-124">[Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k) </span></span>  
 <span data-ttu-id="ca7c8-125">[Walkthrough: Office Programming](../../../csharp/programming-guide/interop/walkthrough-office-programming.md) (Пошаговое руководство. Программирование приложений Office)</span><span class="sxs-lookup"><span data-stu-id="ca7c8-125">[Walkthrough: Office Programming](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)</span></span>

