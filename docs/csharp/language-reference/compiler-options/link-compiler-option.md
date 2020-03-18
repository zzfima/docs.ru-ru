---
title: -link (параметры компилятора C#)
ms.date: 07/20/2015
helpviewer_keywords:
- /l compiler option [C#]
- /link compiler option [C#]
- -l compiler option [C#]
- EmbedInteropTypes
- l compiler option [C#]
- embed interop types [COM Interop]
- -link compiler option [C#]
- link compiler option [C#]
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
ms.openlocfilehash: 4c96f7be5ac500886ea036c93b4651fa814ee58a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970109"
---
# <a name="-link-c-compiler-options"></a><span data-ttu-id="18690-102">-link (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="18690-102">-link (C# Compiler Options)</span></span>
<span data-ttu-id="18690-103">Дает компилятору указание сделать всю информацию о типах COM из указанных сборок доступной компилируемому проекту.</span><span class="sxs-lookup"><span data-stu-id="18690-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18690-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18690-104">Syntax</span></span>  
  
```console  
-link:fileList  
// -or-  
-l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="18690-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="18690-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="18690-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="18690-106">Required.</span></span> <span data-ttu-id="18690-107">Список всех имен файлов сборки, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="18690-107">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="18690-108">Если имя файла содержит пробел, заключите его в кавычки.</span><span class="sxs-lookup"><span data-stu-id="18690-108">If the file name contains a space, enclose the name in quotation marks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18690-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="18690-109">Remarks</span></span>  
 <span data-ttu-id="18690-110">Параметр `-link` позволяет развернуть приложение, содержащее внедренные сведения о типе.</span><span class="sxs-lookup"><span data-stu-id="18690-110">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="18690-111">После этого приложение может использовать типы из сборки среды выполнения, реализующей информацию о внедренных типах, без ссылки на эту сборку.</span><span class="sxs-lookup"><span data-stu-id="18690-111">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="18690-112">Если опубликовано несколько версий сборки среды выполнения, приложение, содержащее сведения о внедренных типах, может работать с различными версиями без перекомпиляции.</span><span class="sxs-lookup"><span data-stu-id="18690-112">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="18690-113">Пример см. в разделе [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](../../../standard/assembly/embed-types-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="18690-113">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](../../../standard/assembly/embed-types-visual-studio.md).</span></span>  
  
 <span data-ttu-id="18690-114">Параметр `-link` особенно полезен при работе с COM-взаимодействием.</span><span class="sxs-lookup"><span data-stu-id="18690-114">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="18690-115">COM-типы внедряются для того, чтобы приложению не требовалась основная сборка взаимодействия (PIA) на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="18690-115">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="18690-116">Параметр `-link` предписывает компилятору внедрить сведения о COM-типах из указанной сборки взаимодействия в полученный скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="18690-116">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="18690-117">COM-тип определяется значением CLSID (GUID).</span><span class="sxs-lookup"><span data-stu-id="18690-117">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="18690-118">Это позволяет запускать приложение на целевом компьютере, где установлены те же COM-типы с такими же значениями CLSID.</span><span class="sxs-lookup"><span data-stu-id="18690-118">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="18690-119">В качестве примера можно привести приложения, автоматизирующие Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="18690-119">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="18690-120">Поскольку в приложениях типа Office значение CLSID обычно не зависит от версии, ваше приложение сможет использовать COM-типы по ссылке до тех пора, пока на целевом компьютере установлена платформа .NET Framework 4 или более поздней версии, а приложение работает с методами, свойствами или событиями, включенными в эти COM-типы.</span><span class="sxs-lookup"><span data-stu-id="18690-120">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="18690-121">Параметр `-link` внедряет только интерфейсы, структуры и делегаты.</span><span class="sxs-lookup"><span data-stu-id="18690-121">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="18690-122">Внедрение COM-классов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="18690-122">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18690-123">Если в коде создается экземпляр внедренного COM-типа, его следует создавать, используя соответствующий интерфейс.</span><span class="sxs-lookup"><span data-stu-id="18690-123">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="18690-124">При попытке создать экземпляр внедренного COM-типа с помощью компонентного класса возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="18690-124">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="18690-125">Чтобы задать параметр `-link` в Visual Studio, добавьте ссылку на сборку и задайте для свойства `Embed Interop Types` значение **true**.</span><span class="sxs-lookup"><span data-stu-id="18690-125">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="18690-126">По умолчанию для свойства `Embed Interop Types` задается значение **false**.</span><span class="sxs-lookup"><span data-stu-id="18690-126">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="18690-127">Ссылаясь на COM-сборку (сборку A), которая, в свою очередь, ссылается на другую COM-сборку (сборку Б), необходимо также добавить ссылку на сборку Б, если выполняется любое из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="18690-127">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
- <span data-ttu-id="18690-128">Тип из сборки A наследуется из типа или реализует интерфейс сборки Б.</span><span class="sxs-lookup"><span data-stu-id="18690-128">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="18690-129">Вызывается поле, свойство, событие или метод, имеющий тип возвращаемого значения или тип параметра из сборки Б.</span><span class="sxs-lookup"><span data-stu-id="18690-129">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="18690-130">Как и параметр компилятора [-reference](./reference-compiler-option.md), параметр компилятора `-link` использует файл ответов Csc.rsp, который ссылается на часто используемые сборки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="18690-130">Like the [-reference](./reference-compiler-option.md) compiler option, the `-link` compiler option uses the Csc.rsp response file, which references frequently used .NET Framework assemblies.</span></span> <span data-ttu-id="18690-131">Если вы не хотите, чтобы компилятор использовал файл Csc.rsp, примените параметр компилятора [-noconfig](./noconfig-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="18690-131">Use the [-noconfig](./noconfig-compiler-option.md) compiler option if you do not want the compiler to use the Csc.rsp file.</span></span>  
  
 <span data-ttu-id="18690-132">Краткой формой `-link` является `-l`.</span><span class="sxs-lookup"><span data-stu-id="18690-132">The short form of `-link` is `-l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="18690-133">Универсальные и внедренные типы</span><span class="sxs-lookup"><span data-stu-id="18690-133">Generics and Embedded Types</span></span>  
 <span data-ttu-id="18690-134">В следующих разделах описаны ограничения на использование универсальных типов в приложениях с внедренными типами взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="18690-134">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="18690-135">Универсальные интерфейсы</span><span class="sxs-lookup"><span data-stu-id="18690-135">Generic Interfaces</span></span>  
 <span data-ttu-id="18690-136">Использовать универсальные интерфейсы, внедренные из сборки взаимодействия, нельзя.</span><span class="sxs-lookup"><span data-stu-id="18690-136">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="18690-137">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="18690-137">This is shown in the following example.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#1)]  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="18690-138">Типы с универсальными параметрами</span><span class="sxs-lookup"><span data-stu-id="18690-138">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="18690-139">Типы с универсальным параметром, тип которого внедрен из сборки взаимодействия, нельзя использовать, если он относится к внешней сборке.</span><span class="sxs-lookup"><span data-stu-id="18690-139">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="18690-140">Это ограничение не относится к интерфейсам.</span><span class="sxs-lookup"><span data-stu-id="18690-140">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="18690-141">Например, рассмотрим интерфейс <xref:Microsoft.Office.Interop.Excel.Range>, который определен в сборке <xref:Microsoft.Office.Interop.Excel>.</span><span class="sxs-lookup"><span data-stu-id="18690-141">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="18690-142">Если библиотека содержит внедренные типы взаимодействия из сборки <xref:Microsoft.Office.Interop.Excel> и предоставляет метод, возвращающий универсальный тип с параметром, типом которого является интерфейс <xref:Microsoft.Office.Interop.Excel.Range>, этот метод должен возвращать универсальный интерфейс, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="18690-142">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs#2)]  
[!code-csharp[VbLinkCompilerCS#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs#3)]  
[!code-csharp[VbLinkCompilerCS#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs#4)]  
  
 <span data-ttu-id="18690-143">В следующем примере клиентский код может вызывать метод, возвращающий универсальный интерфейс <xref:System.Collections.IList> без ошибок.</span><span class="sxs-lookup"><span data-stu-id="18690-143">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#5)]  
  
## <a name="example"></a><span data-ttu-id="18690-144">Пример</span><span class="sxs-lookup"><span data-stu-id="18690-144">Example</span></span>  
 <span data-ttu-id="18690-145">Следующий код компилирует исходный файл `OfficeApp.cs` и ссылочные сборки из `COMData1.dll` и `COMData2.dll` и создает, таким образом, файл `OfficeApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="18690-145">The following code compiles source file `OfficeApp.cs` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```csharp  
csc -link:COMData1.dll,COMData2.dll -out:OfficeApp.exe OfficeApp.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="18690-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="18690-146">See also</span></span>

- [<span data-ttu-id="18690-147">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="18690-147">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="18690-148">Пошаговое руководство. Внедрение данных о типах из управляемых сборок</span><span class="sxs-lookup"><span data-stu-id="18690-148">Walkthrough: Embedding Types from Managed Assemblies</span></span>](../../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="18690-149">-reference (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="18690-149">-reference (C# Compiler Options)</span></span>](./reference-compiler-option.md)
- [<span data-ttu-id="18690-150">-noconfig (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="18690-150">-noconfig (C# Compiler Options)</span></span>](./noconfig-compiler-option.md)
- [<span data-ttu-id="18690-151">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="18690-151">Command-line Building With csc.exe</span></span>](./command-line-building-with-csc-exe.md)
- [<span data-ttu-id="18690-152">Общие сведения о взаимодействии</span><span class="sxs-lookup"><span data-stu-id="18690-152">Interoperability Overview</span></span>](../../programming-guide/interop/interoperability-overview.md)
