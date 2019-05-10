---
title: Практическое руководство. Ссылаться на COM-объекты из Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: 8ff2a3a4e9249b324dac9b244cab68ae8f8e1cab
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624837"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="b6ef6-102">Практическое руководство. Ссылаться на COM-объекты из Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b6ef6-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="b6ef6-103">В Visual Basic Добавление ссылок на COM-объекты, имеющие библиотеки типов необходимо создать сборку взаимодействия для COM-библиотеки.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-103">In Visual Basic, adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="b6ef6-104">Ссылки на члены объекта COM направляются в сборку взаимодействия и затем перенаправляется на фактический объект COM.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="b6ef6-105">Ответы от COM-объекта направляются в сборку взаимодействия и пересылаются в вашей [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] application.</span></span>  
  
 <span data-ttu-id="b6ef6-106">COM-объект можно ссылаться без использования сборки взаимодействия, внедряя сведения о типе для COM-объекта в сборку .NET.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="b6ef6-107">Чтобы внедрить сведения о типе, присвойте `Embed Interop Types` свойства `True` для ссылки на COM-объект.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="b6ef6-108">При компиляции с помощью компилятора командной строки, используйте `/link` параметр, чтобы ссылаться на библиотеки COM.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="b6ef6-109">Дополнительные сведения см. в разделе [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="b6ef6-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 <span data-ttu-id="b6ef6-110">Visual Basic автоматически создает сборки взаимодействия, при добавлении ссылки на библиотеку типов из интегрированной среде разработки (IDE).</span><span class="sxs-lookup"><span data-stu-id="b6ef6-110">Visual Basic automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="b6ef6-111">При работе из командной строки, можно использовать служебную программу Tlbimp для создания сборки взаимодействия вручную.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="b6ef6-112">Добавление ссылок на COM-объекты</span><span class="sxs-lookup"><span data-stu-id="b6ef6-112">To add references to COM objects</span></span>  
  
1. <span data-ttu-id="b6ef6-113">На **проекта** меню, выберите **добавить ссылку** и нажмите кнопку **COM** вкладки в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2. <span data-ttu-id="b6ef6-114">Выберите компонент, который вы хотите использовать в списке COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3. <span data-ttu-id="b6ef6-115">Чтобы упростить доступ к сборке взаимодействия, добавьте `Imports` в начало класса или модуля, в котором используется COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="b6ef6-116">Например, в следующем примере кода импортирует пространство имен `INKEDLib` для объектов, на которые ссылается `Microsoft InkEdit Control 1.0` библиотеки.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#40)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="b6ef6-117">Чтобы создать сборку взаимодействия, при помощи средства Tlbimp</span><span class="sxs-lookup"><span data-stu-id="b6ef6-117">To create an interop assembly using Tlbimp</span></span>  
  
1. <span data-ttu-id="b6ef6-118">Добавьте расположение Tlbimp в путь поиска, если он уже не является частью пути поиска, и вы находитесь не в настоящее время в каталоге, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2. <span data-ttu-id="b6ef6-119">Вызовите программу Tlbimp из командной строки, указав следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="b6ef6-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    - <span data-ttu-id="b6ef6-120">Имя и расположение библиотеки DLL, которая содержит библиотеки типов</span><span class="sxs-lookup"><span data-stu-id="b6ef6-120">Name and location of the DLL that contains the type library</span></span>  
  
    - <span data-ttu-id="b6ef6-121">Имя и расположение пространства имен, где должны размещаться данные</span><span class="sxs-lookup"><span data-stu-id="b6ef6-121">Name and location of the namespace where the information should be placed</span></span>  
  
    - <span data-ttu-id="b6ef6-122">Имя и расположение целевой сборки взаимодействия</span><span class="sxs-lookup"><span data-stu-id="b6ef6-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="b6ef6-123">Примером является следующий код:</span><span class="sxs-lookup"><span data-stu-id="b6ef6-123">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="b6ef6-124">Tlbimp можно использовать для создания сборки взаимодействия для библиотек типов, даже для отмены регистрации COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="b6ef6-125">Тем не менее COM-объекты, на который ссылается сборки взаимодействия должны быть правильно зарегистрированы на компьютере, где они будут использоваться.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="b6ef6-126">COM-объект можно зарегистрировать с помощью служебной программы Regsvr32, включенные в операционную систему Windows.</span><span class="sxs-lookup"><span data-stu-id="b6ef6-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6ef6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b6ef6-127">See also</span></span>

- [<span data-ttu-id="b6ef6-128">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="b6ef6-128">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
- [<span data-ttu-id="b6ef6-129">Tlbimp.exe (программа экспорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="b6ef6-129">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="b6ef6-130">Tlbexp.exe (программа экспорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="b6ef6-130">Tlbexp.exe (Type Library Exporter)</span></span>](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="b6ef6-131">Пошаговое руководство: Реализация наследования с использованием COM-объектов</span><span class="sxs-lookup"><span data-stu-id="b6ef6-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="b6ef6-132">Устранение неполадок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="b6ef6-132">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
- [<span data-ttu-id="b6ef6-133">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="b6ef6-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
