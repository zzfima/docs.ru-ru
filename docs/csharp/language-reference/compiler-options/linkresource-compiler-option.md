---
title: "-linkresource (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /linkresource
dev_langs:
- CSharp
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
caps.latest.revision: 17
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
ms.openlocfilehash: 022d6c1a53eab98fc033c902f903e7bc66e6da3f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="linkresource-c-compiler-options"></a><span data-ttu-id="3a49a-102">/linkresource (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="3a49a-102">/linkresource (C# Compiler Options)</span></span>
<span data-ttu-id="3a49a-103">Создает в выходном файле ссылку на ресурс платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a49a-103">Creates a link to a .NET Framework resource in the output file.</span></span> <span data-ttu-id="3a49a-104">Файл ресурсов не добавляется в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="3a49a-104">The resource file is not added to the output file.</span></span> <span data-ttu-id="3a49a-105">Этот параметр отличается от параметра [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md), который внедряет файл ресурсов в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="3a49a-105">This differs from the [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) option which does embed a resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a49a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a49a-106">Syntax</span></span>  
  
```console  
/linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3a49a-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3a49a-107">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="3a49a-108">Файл ресурсов .NET Framework, ссылку на который необходимо создать из сборки.</span><span class="sxs-lookup"><span data-stu-id="3a49a-108">The .NET Framework resource file to which you want to link from the assembly.</span></span>  
  
 <span data-ttu-id="3a49a-109">`identifier` (необязательно)</span><span class="sxs-lookup"><span data-stu-id="3a49a-109">`identifier` (optional)</span></span>  
 <span data-ttu-id="3a49a-110">Логическое имя ресурса, используемое для его загрузки.</span><span class="sxs-lookup"><span data-stu-id="3a49a-110">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="3a49a-111">По умолчанию используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="3a49a-111">The default is the name of the file.</span></span>  
  
 <span data-ttu-id="3a49a-112">`accessibility-modifier` (необязательно)</span><span class="sxs-lookup"><span data-stu-id="3a49a-112">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="3a49a-113">Доступность ресурса: "public" (открытый) или "private" (закрытый).</span><span class="sxs-lookup"><span data-stu-id="3a49a-113">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="3a49a-114">Значение по умолчанию — "public" (открытый).</span><span class="sxs-lookup"><span data-stu-id="3a49a-114">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a49a-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="3a49a-115">Remarks</span></span>  
 <span data-ttu-id="3a49a-116">По умолчанию связанные ресурсы в сборке открыты, если они создавались с помощью компилятора C#.</span><span class="sxs-lookup"><span data-stu-id="3a49a-116">By default, linked resources are public in the assembly when they are created with the C# compiler.</span></span> <span data-ttu-id="3a49a-117">Чтобы сделать ресурс закрытым, укажите параметр `private` в качестве модификатора доступа.</span><span class="sxs-lookup"><span data-stu-id="3a49a-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="3a49a-118">Модификаторы, отличные от `public` или `private`, не допускаются.</span><span class="sxs-lookup"><span data-stu-id="3a49a-118">No other modifier other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="3a49a-119">Параметр **/linkresource** требует одного из параметров [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md), отличного от **/target:module**.</span><span class="sxs-lookup"><span data-stu-id="3a49a-119">**/linkresource** requires one of the [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) options other than **/target:module**.</span></span>  
  
 <span data-ttu-id="3a49a-120">Если `filename` является файлом ресурсов .NET Framework, созданным, например, с помощью [Resgen.exe](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) или в среде разработки, то к нему можно обращаться с помощью членов пространства имен <xref:System.Resources>.</span><span class="sxs-lookup"><span data-stu-id="3a49a-120">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="3a49a-121">Для получения дополнительной информации см. <xref:System.Resources.ResourceManager?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="3a49a-121">For more information, see <xref:System.Resources.ResourceManager?displayProperty=fullName>.</span></span> <span data-ttu-id="3a49a-122">Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте методы `GetManifestResource`* в классе <xref:System.Reflection.Assembly>.</span><span class="sxs-lookup"><span data-stu-id="3a49a-122">For all other resources, use the `GetManifestResource`* methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="3a49a-123">Файл, указанный в параметре `filename`, может иметь любой формат.</span><span class="sxs-lookup"><span data-stu-id="3a49a-123">The file specified in `filename` can be any format.</span></span> <span data-ttu-id="3a49a-124">Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки.</span><span class="sxs-lookup"><span data-stu-id="3a49a-124">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span> <span data-ttu-id="3a49a-125">Во втором из следующих примеров показывается, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="3a49a-125">The second of the following examples shows how to do this.</span></span> <span data-ttu-id="3a49a-126">Это действие можно также выполнить в компоновщике сборок.</span><span class="sxs-lookup"><span data-stu-id="3a49a-126">You can do the same thing in the Assembly Linker.</span></span> <span data-ttu-id="3a49a-127">В третьем из следующих примеров показывается, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="3a49a-127">The third of the following examples shows how to do this.</span></span> <span data-ttu-id="3a49a-128">Дополнительные сведения см. в разделах [Al.exe (компоновщик сборок)](https://msdn.microsoft.com/library/c405shex) и [Работа со сборками и глобальным кэшем сборок](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="3a49a-128">For more information, see [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) and [Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span></span>  
  
 <span data-ttu-id="3a49a-129">**/linkres** является краткой формой **/linkresource**.</span><span class="sxs-lookup"><span data-stu-id="3a49a-129">**/linkres** is the short form of **/linkresource**.</span></span>  
  
 <span data-ttu-id="3a49a-130">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="3a49a-130">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a49a-131">Пример</span><span class="sxs-lookup"><span data-stu-id="3a49a-131">Example</span></span>  
 <span data-ttu-id="3a49a-132">Компиляция `in.cs` и создание ссылки на файл ресурсов `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="3a49a-132">Compile `in.cs` and link to resource file `rf.resource`:</span></span>  
  
```console  
csc /linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a><span data-ttu-id="3a49a-133">Пример</span><span class="sxs-lookup"><span data-stu-id="3a49a-133">Example</span></span>  
 <span data-ttu-id="3a49a-134">Скомпилируйте `A.cs` в библиотеку DLL, создайте ссылку на машинную библиотеку N.dll и поместите выходные данные в глобальный кэш сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="3a49a-134">Compile `A.cs` into a DLL, link to a native DLL N.dll, and put the output in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="3a49a-135">В этом примере оба файла A.dll и N.dll будут расположены в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="3a49a-135">In this example, both A.dll and N.dll will reside in the GAC.</span></span>  
  
```console  
csc /linkresource:N.dll /t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a><span data-ttu-id="3a49a-136">Пример</span><span class="sxs-lookup"><span data-stu-id="3a49a-136">Example</span></span>  
 <span data-ttu-id="3a49a-137">В этом примере выполняются те же действия, что и в предыдущем примере, но с использованием параметров компоновщика сборок.</span><span class="sxs-lookup"><span data-stu-id="3a49a-137">This example does the same thing as the previous one, but by using Assembly Linker options.</span></span>  
  
```console  
csc /t:module A.cs  
al /out:A.dll A.netmodule /link:N.dll   
gacutil -i A.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a49a-138">См. также</span><span class="sxs-lookup"><span data-stu-id="3a49a-138">See Also</span></span>  
 <span data-ttu-id="3a49a-139">[Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="3a49a-139">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="3a49a-140">[Al.exe (компоновщик сборок)](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="3a49a-140">[Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
 <span data-ttu-id="3a49a-141">[Работа со сборками и глобальным кэшем сборок](../../../framework/app-domains/working-with-assemblies-and-the-gac.md) </span><span class="sxs-lookup"><span data-stu-id="3a49a-141">[Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md) </span></span>  
 [<span data-ttu-id="3a49a-142">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="3a49a-142">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

