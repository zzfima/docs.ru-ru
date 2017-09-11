---
title: "Практическое руководство: ссылка на объект COM в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- COM interop, referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5f7f1112161d9be995cc80378ad9dd95c522198d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="e92dc-102">Практическое руководство. Ссылка на COM-объект в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e92dc-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="e92dc-103">В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], добавление ссылок на COM-объекты, имеющие библиотеки типов необходимо создать сборку взаимодействия для COM-библиотеки.</span><span class="sxs-lookup"><span data-stu-id="e92dc-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="e92dc-104">Ссылки на члены объекта COM направляются в сборку взаимодействия и пересылаются на фактическое COM-объект.</span><span class="sxs-lookup"><span data-stu-id="e92dc-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="e92dc-105">Отклики от объекта COM направляются в сборку взаимодействия и пересылаются на [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="e92dc-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] application.</span></span>  
  
 <span data-ttu-id="e92dc-106">COM-объект можно ссылаться без использования сборки взаимодействия путем встраивания сведения о типе для COM-объекта в сборку .NET.</span><span class="sxs-lookup"><span data-stu-id="e92dc-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="e92dc-107">Чтобы внедрить сведения о типе, присвойте `Embed Interop Types` свойства `True` для ссылки на COM-объект.</span><span class="sxs-lookup"><span data-stu-id="e92dc-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="e92dc-108">Если компиляция производится с помощью компилятора командной строки, используйте `/link` возможность ссылки на библиотеку COM.</span><span class="sxs-lookup"><span data-stu-id="e92dc-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="e92dc-109">Дополнительные сведения см. в разделе [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="e92dc-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="e92dc-110">автоматически создает сборки взаимодействия при добавлении ссылки на библиотеку типов из интегрированной среды разработки (IDE).</span><span class="sxs-lookup"><span data-stu-id="e92dc-110"> automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="e92dc-111">При работе из командной строки можно использовать средство Tlbimp для создания сборок взаимодействия вручную.</span><span class="sxs-lookup"><span data-stu-id="e92dc-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="e92dc-112">Добавление ссылок на COM-объекты</span><span class="sxs-lookup"><span data-stu-id="e92dc-112">To add references to COM objects</span></span>  
  
1.  <span data-ttu-id="e92dc-113">На **проекта** меню, выберите **добавить ссылку** и нажмите кнопку **COM** вкладки в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="e92dc-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2.  <span data-ttu-id="e92dc-114">Выберите компонент, который вы хотите использовать в списке COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="e92dc-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3.  <span data-ttu-id="e92dc-115">Для упрощения доступа к сборке взаимодействия добавьте `Imports` инструкции в начало класса или модуля, в котором будет использоваться COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="e92dc-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="e92dc-116">Например, в следующем примере кода импортирует пространство имен `INKEDLib` для объектов, указанных в `Microsoft InkEdit Control 1.0` библиотеки.</span><span class="sxs-lookup"><span data-stu-id="e92dc-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     <span data-ttu-id="e92dc-117">[!code-vb[VbVbalrInterop&#40;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e92dc-117">[!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]</span></span>  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="e92dc-118">Чтобы создать сборку взаимодействия при помощи средства Tlbimp</span><span class="sxs-lookup"><span data-stu-id="e92dc-118">To create an interop assembly using Tlbimp</span></span>  
  
1.  <span data-ttu-id="e92dc-119">Добавьте расположение Tlbimp в путь поиска, если он уже не является частью пути поиска и настоящее время вы не в каталоге, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="e92dc-119">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2.  <span data-ttu-id="e92dc-120">Вызовите программу Tlbimp из командной строки, указав следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e92dc-120">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    -   <span data-ttu-id="e92dc-121">Имя и расположение библиотеки DLL, содержащего библиотеку типов</span><span class="sxs-lookup"><span data-stu-id="e92dc-121">Name and location of the DLL that contains the type library</span></span>  
  
    -   <span data-ttu-id="e92dc-122">Имя и расположение пространства имен, где должна быть размещена информация</span><span class="sxs-lookup"><span data-stu-id="e92dc-122">Name and location of the namespace where the information should be placed</span></span>  
  
    -   <span data-ttu-id="e92dc-123">Имя и расположение целевой сборки взаимодействия</span><span class="sxs-lookup"><span data-stu-id="e92dc-123">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="e92dc-124">Примером является следующий код:</span><span class="sxs-lookup"><span data-stu-id="e92dc-124">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="e92dc-125">Tlbimp можно использовать для создания сборок взаимодействия для библиотек типов, даже для незарегистрированных COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="e92dc-125">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="e92dc-126">Тем не менее COM-объекты, на которые ссылается на сборки взаимодействия должны быть правильно зарегистрированы на компьютере, где они будут использоваться.</span><span class="sxs-lookup"><span data-stu-id="e92dc-126">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="e92dc-127">Можно зарегистрировать объект COM при помощи программы Regsvr32, входящий в состав операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="e92dc-127">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e92dc-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e92dc-128">See Also</span></span>  
 <span data-ttu-id="e92dc-129">[Взаимодействие COM](../../../visual-basic/programming-guide/com-interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="e92dc-129">[COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span></span>  
<span data-ttu-id="e92dc-130"> [Tlbimp.exe (программа импорта библиотек типов)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) </span><span class="sxs-lookup"><span data-stu-id="e92dc-130"> [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) </span></span>  
<span data-ttu-id="e92dc-131"> [Tlbexp.exe (программа экспорта библиотек типов)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d) </span><span class="sxs-lookup"><span data-stu-id="e92dc-131"> [Tlbexp.exe (Type Library Exporter)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d) </span></span>  
<span data-ttu-id="e92dc-132"> [Пошаговое руководство: Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span><span class="sxs-lookup"><span data-stu-id="e92dc-132"> [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span></span>  
<span data-ttu-id="e92dc-133"> [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md) </span><span class="sxs-lookup"><span data-stu-id="e92dc-133"> [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md) </span></span>  
<span data-ttu-id="e92dc-134"> [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span><span class="sxs-lookup"><span data-stu-id="e92dc-134"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span></span>
