---
title: "Практическое руководство. Ссылка на COM-объект в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 694bd74e2b5ae374269accd845fe9178958bf56c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="15f08-102">Практическое руководство. Ссылка на COM-объект в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15f08-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="15f08-103">В [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], добавление ссылок на COM-объекты, имеющие библиотеки типов необходимо создать сборку взаимодействия для COM-библиотеки.</span><span class="sxs-lookup"><span data-stu-id="15f08-103">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="15f08-104">Ссылки на члены объекта COM направляются в сборку взаимодействия и пересылаются на фактическое COM-объект.</span><span class="sxs-lookup"><span data-stu-id="15f08-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="15f08-105">Ответы из COM-объекта направляются в сборку взаимодействия и пересылаются в вашей [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="15f08-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] application.</span></span>  
  
 <span data-ttu-id="15f08-106">COM-объект можно ссылаться без использования сборки взаимодействия, внедрение сведений о типах COM-объекта в сборку .NET.</span><span class="sxs-lookup"><span data-stu-id="15f08-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="15f08-107">Чтобы внедрить сведения о типе, присвойте `Embed Interop Types` свойства `True` для ссылки на COM-объект.</span><span class="sxs-lookup"><span data-stu-id="15f08-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="15f08-108">При компиляции с помощью компилятора командной строки используйте `/link` для создания ссылки на библиотеку COM.</span><span class="sxs-lookup"><span data-stu-id="15f08-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="15f08-109">Дополнительные сведения см. в разделе [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="15f08-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="15f08-110">автоматически создает сборки взаимодействия при добавлении ссылки на библиотеку типов из интегрированной среды разработки (IDE).</span><span class="sxs-lookup"><span data-stu-id="15f08-110"> automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="15f08-111">При работе в командной строке, можно использовать служебную программу Tlbimp для создания сборки взаимодействия вручную.</span><span class="sxs-lookup"><span data-stu-id="15f08-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="15f08-112">Для добавления ссылок на COM-объекты</span><span class="sxs-lookup"><span data-stu-id="15f08-112">To add references to COM objects</span></span>  
  
1.  <span data-ttu-id="15f08-113">На **проекта** меню, выберите **добавить ссылку** и нажмите кнопку **COM** вкладка в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="15f08-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2.  <span data-ttu-id="15f08-114">Выберите компонент, который вы хотите использовать в списке COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="15f08-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3.  <span data-ttu-id="15f08-115">Для упрощения доступа к сборке взаимодействия, добавьте `Imports` в начало класса или модуля, в котором будет использоваться COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="15f08-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="15f08-116">Например, в следующем примере кода выполняется импорт пространства имен `INKEDLib` для объектов, указанных в `Microsoft InkEdit Control 1.0` библиотеки.</span><span class="sxs-lookup"><span data-stu-id="15f08-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="15f08-117">Чтобы создать сборку взаимодействия с помощью Tlbimp</span><span class="sxs-lookup"><span data-stu-id="15f08-117">To create an interop assembly using Tlbimp</span></span>  
  
1.  <span data-ttu-id="15f08-118">Добавьте расположение Tlbimp в путь поиска, если он уже не является частью пути поиска, и вы находитесь не в настоящее время в каталоге, где он расположен.</span><span class="sxs-lookup"><span data-stu-id="15f08-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2.  <span data-ttu-id="15f08-119">Вызовите программу Tlbimp из командной строки, указав следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="15f08-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    -   <span data-ttu-id="15f08-120">Имя и расположение библиотеки DLL, которая содержит библиотеку типов</span><span class="sxs-lookup"><span data-stu-id="15f08-120">Name and location of the DLL that contains the type library</span></span>  
  
    -   <span data-ttu-id="15f08-121">Имя и расположение пространства имен, где должны размещаться данные</span><span class="sxs-lookup"><span data-stu-id="15f08-121">Name and location of the namespace where the information should be placed</span></span>  
  
    -   <span data-ttu-id="15f08-122">Имя и расположение целевой сборки взаимодействия</span><span class="sxs-lookup"><span data-stu-id="15f08-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="15f08-123">Примером является следующий код:</span><span class="sxs-lookup"><span data-stu-id="15f08-123">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="15f08-124">Tlbimp можно использовать для создания сборок взаимодействия для библиотек типов, даже для незарегистрированных COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="15f08-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="15f08-125">Тем не менее COM-объекты, на который ссылается сборки взаимодействия должны быть правильно зарегистрированы на компьютере, где они будут использоваться.</span><span class="sxs-lookup"><span data-stu-id="15f08-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="15f08-126">COM-объект можно зарегистрировать с помощью служебной программы Regsvr32, входящий в состав операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="15f08-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f08-127">См. также</span><span class="sxs-lookup"><span data-stu-id="15f08-127">See Also</span></span>  
 [<span data-ttu-id="15f08-128">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="15f08-128">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="15f08-129">Tlbimp.exe (программа экспорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="15f08-129">Tlbimp.exe (Type Library Importer)</span></span>](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 [<span data-ttu-id="15f08-130">Tlbexp.exe (программа экспорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="15f08-130">Tlbexp.exe (Type Library Exporter)</span></span>](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [<span data-ttu-id="15f08-131">Пошаговое руководство. Реализация наследования с использованием COM-объектов</span><span class="sxs-lookup"><span data-stu-id="15f08-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="15f08-132">Устранение неполадок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="15f08-132">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [<span data-ttu-id="15f08-133">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="15f08-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
