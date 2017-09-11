---
title: "/ LINK (Visual Basic) | Документы Microsoft"
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
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
caps.latest.revision: 27
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
ms.openlocfilehash: 71ecefc898ca37cbf7299d97518e1ce2547a58da
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="link-visual-basic"></a><span data-ttu-id="6664a-102">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6664a-102">/link (Visual Basic)</span></span>
<span data-ttu-id="6664a-103">Указывает компилятору сделать доступными для проекта, компилируемого в текущий момент сведения о типах COM в указанных сборках.</span><span class="sxs-lookup"><span data-stu-id="6664a-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6664a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6664a-104">Syntax</span></span>  
  
```  
/link:fileList  
' -or-  
/l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="6664a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6664a-105">Arguments</span></span>  
  
|<span data-ttu-id="6664a-106">Термин</span><span class="sxs-lookup"><span data-stu-id="6664a-106">Term</span></span>|<span data-ttu-id="6664a-107">Определение</span><span class="sxs-lookup"><span data-stu-id="6664a-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="6664a-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="6664a-108">Required.</span></span> <span data-ttu-id="6664a-109">Разделенный запятыми список имен файлов сборки.</span><span class="sxs-lookup"><span data-stu-id="6664a-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="6664a-110">Если имя файла содержит пробел, заключите имя в кавычки.</span><span class="sxs-lookup"><span data-stu-id="6664a-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6664a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="6664a-111">Remarks</span></span>  
 <span data-ttu-id="6664a-112">`/link` Позволяет развернуть приложение, содержащее внедренные сведения о типе.</span><span class="sxs-lookup"><span data-stu-id="6664a-112">The `/link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="6664a-113">Затем приложение может использовать типы в сборке среды выполнения, реализующие внедренные сведения о типах, не ссылаясь на сборку среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6664a-113">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="6664a-114">Если опубликовано несколько версий сборки среды выполнения, приложение, содержащее внедренные сведения о типах может работать с различными версиями без перекомпиляции.</span><span class="sxs-lookup"><span data-stu-id="6664a-114">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="6664a-115">Например, в разделе [Пошаговое руководство: внедрение типов из управляемых сборок](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span><span class="sxs-lookup"><span data-stu-id="6664a-115">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
 <span data-ttu-id="6664a-116">С помощью `/link` параметр особенно полезен при работе с COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6664a-116">Using the `/link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="6664a-117">Типы COM можно внедрять, чтобы приложение больше не требуется основной сборки взаимодействия (PIA) на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6664a-117">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="6664a-118">`/link` Предписывает компилятору внедрить сведения о типах COM из указанной сборки взаимодействия в полученный скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="6664a-118">The `/link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="6664a-119">Тип модели COM определяется значение CLSID (идентификатор GUID).</span><span class="sxs-lookup"><span data-stu-id="6664a-119">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="6664a-120">В результате приложение может выполняться на конечном компьютере, на который установлен те же типы COM с теми же значениями CLSID.</span><span class="sxs-lookup"><span data-stu-id="6664a-120">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="6664a-121">Приложения, автоматизирующие Microsoft Office — хороший пример.</span><span class="sxs-lookup"><span data-stu-id="6664a-121">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="6664a-122">Так приложений, таких как Office обычно одно и то же значение CLSID в различных версиях, приложение может использовать ссылочных типов COM, как долго, как .NET Framework 4 или более поздней версии установлен на целевом компьютере и приложение использует методы, свойства или события, включенные в ссылочные типы COM.</span><span class="sxs-lookup"><span data-stu-id="6664a-122">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="6664a-123">`/link` Позволяет внедрять только интерфейсы, структуры и делегаты.</span><span class="sxs-lookup"><span data-stu-id="6664a-123">The `/link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="6664a-124">Внедрение COM-классов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6664a-124">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6664a-125">При создании экземпляра внедренного типа COM в коде, необходимо создать экземпляр, используя соответствующий интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6664a-125">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="6664a-126">Попытка создать экземпляр внедренного типа COM с помощью компонентного класса приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="6664a-126">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="6664a-127">Чтобы задать `/link` параметр в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], добавьте ссылку на сборку и задайте `Embed Interop Types` свойства **true**.</span><span class="sxs-lookup"><span data-stu-id="6664a-127">To set the `/link` option in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="6664a-128">Значение по умолчанию для `Embed Interop Types` свойство **false**.</span><span class="sxs-lookup"><span data-stu-id="6664a-128">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="6664a-129">Если ссылка на сборку COM (сборку A) который сам ссылается на другую сборку COM (сборку Б), необходимо также ссылку на сборку Б, если выполняется любое из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="6664a-129">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
-   <span data-ttu-id="6664a-130">Из сборки A тип наследуется от типа или реализует интерфейс из сборки б.</span><span class="sxs-lookup"><span data-stu-id="6664a-130">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="6664a-131">Вызывается поле, свойство, событие или метод, который имеет возвращаемый тип или параметр типа из сборки Б.</span><span class="sxs-lookup"><span data-stu-id="6664a-131">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="6664a-132">Используйте [/LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) указать каталог, в котором находится один или несколько ссылки на сборки.</span><span class="sxs-lookup"><span data-stu-id="6664a-132">Use [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="6664a-133">Как [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) параметр компилятора `/link` использует файл ответов Vbc.rsp, который ссылается на часто используемые [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборки.</span><span class="sxs-lookup"><span data-stu-id="6664a-133">Like the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) compiler option, the `/link` compiler option uses the Vbc.rsp response file, which references frequently used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies.</span></span> <span data-ttu-id="6664a-134">Используйте [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) параметр компилятора, если не хотите, чтобы компилятор использовал файл Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="6664a-134">Use the [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.</span></span>  
  
 <span data-ttu-id="6664a-135">Краткая форма `/link` — `/l`.</span><span class="sxs-lookup"><span data-stu-id="6664a-135">The short form of `/link` is `/l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="6664a-136">Универсальные и внедренные типы</span><span class="sxs-lookup"><span data-stu-id="6664a-136">Generics and Embedded Types</span></span>  
 <span data-ttu-id="6664a-137">В следующих разделах описаны ограничения на использование универсальных типов в приложениях, внедрение типов взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6664a-137">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="6664a-138">Универсальные интерфейсы</span><span class="sxs-lookup"><span data-stu-id="6664a-138">Generic Interfaces</span></span>  
 <span data-ttu-id="6664a-139">Нельзя использовать универсальные интерфейсы, внедренные из сборки взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6664a-139">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="6664a-140">Эти действия показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6664a-140">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="6664a-141">[!code-vb[VbLinkCompiler&#1;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="6664a-141">[!code-vb[VbLinkCompiler#1](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]</span></span>  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="6664a-142">Типы с универсальными параметрами</span><span class="sxs-lookup"><span data-stu-id="6664a-142">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="6664a-143">Типы, которые имеют общий параметр, тип которого внедрен из сборки взаимодействия не может использоваться при, тип из внешней сборки.</span><span class="sxs-lookup"><span data-stu-id="6664a-143">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="6664a-144">Это ограничение не применяется к интерфейсам.</span><span class="sxs-lookup"><span data-stu-id="6664a-144">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="6664a-145">Например, рассмотрим <xref:Microsoft.Office.Interop.Excel.Range>интерфейс, который определен в <xref:Microsoft.Office.Interop.Excel>сборки.</xref:Microsoft.Office.Interop.Excel> </xref:Microsoft.Office.Interop.Excel.Range></span><span class="sxs-lookup"><span data-stu-id="6664a-145">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="6664a-146">Если библиотека содержит внедренные типы взаимодействия из <xref:Microsoft.Office.Interop.Excel>и предоставляет метод, возвращающий универсальный тип, который имеет параметр, тип которого является <xref:Microsoft.Office.Interop.Excel.Range>интерфейс, что метод должен возвращать универсальный интерфейс, как показано в следующем примере кода.</xref:Microsoft.Office.Interop.Excel.Range> </xref:Microsoft.Office.Interop.Excel></span><span class="sxs-lookup"><span data-stu-id="6664a-146">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 <span data-ttu-id="6664a-147">[!code-vb[VbLinkCompiler&#2;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="6664a-147">[!code-vb[VbLinkCompiler#2](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]</span></span>  
<span data-ttu-id="6664a-148">[!code-vb[VbLinkCompiler&#3;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="6664a-148">[!code-vb[VbLinkCompiler#3](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]</span></span>  
<span data-ttu-id="6664a-149">[!code-vb[VbLinkCompiler&#4;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="6664a-149">[!code-vb[VbLinkCompiler#4](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]</span></span>  
  
 <span data-ttu-id="6664a-150">В следующем примере клиентский код может вызывать метод, возвращающий <xref:System.Collections.IList>универсальный интерфейс без ошибок.</xref:System.Collections.IList></span><span class="sxs-lookup"><span data-stu-id="6664a-150">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 <span data-ttu-id="6664a-151">[!code-vb[VbLinkCompiler&#5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="6664a-151">[!code-vb[VbLinkCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="6664a-152">Пример</span><span class="sxs-lookup"><span data-stu-id="6664a-152">Example</span></span>  
 <span data-ttu-id="6664a-153">Следующий код компилирует исходный файл `OfficeApp.vb` и ссылки на сборки из `COMData1.dll` и `COMData2.dll` для создания `OfficeApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="6664a-153">The following code compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```vb  
vbc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6664a-154">См. также</span><span class="sxs-lookup"><span data-stu-id="6664a-154">See Also</span></span>  
 <span data-ttu-id="6664a-155">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="6664a-155">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="6664a-156"> [Пошаговое руководство: Внедрение типов из управляемых сборок](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21) </span><span class="sxs-lookup"><span data-stu-id="6664a-156"> [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21) </span></span>  
<span data-ttu-id="6664a-157"> [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="6664a-157"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="6664a-158"> [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="6664a-158"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="6664a-159"> [/ LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) </span><span class="sxs-lookup"><span data-stu-id="6664a-159"> [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) </span></span>  
<span data-ttu-id="6664a-160"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="6664a-160"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="6664a-161"> [Знакомство с COM-взаимодействием](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)</span><span class="sxs-lookup"><span data-stu-id="6664a-161"> [Introduction to COM Interop](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)</span></span>
