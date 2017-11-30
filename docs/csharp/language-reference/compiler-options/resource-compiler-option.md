---
title: "-resource (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 726956275436e22723bc32b98b2b8b7c7df5fb12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="resource-c-compiler-options"></a><span data-ttu-id="e0ad0-102">/resource (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="e0ad0-102">/resource (C# Compiler Options)</span></span>
<span data-ttu-id="e0ad0-103">Внедряет указанный ресурс в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-103">Embeds the specified resource into the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0ad0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0ad0-104">Syntax</span></span>  
  
```console  
/resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e0ad0-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e0ad0-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="e0ad0-106">Файл ресурсов платформы .NET Framework, который требуется внедрить в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-106">The .NET Framework resource file that you want to embed in the output file.</span></span>  
  
 <span data-ttu-id="e0ad0-107">`identifier` (необязательно)</span><span class="sxs-lookup"><span data-stu-id="e0ad0-107">`identifier` (optional)</span></span>  
 <span data-ttu-id="e0ad0-108">Логическое имя ресурса, используемое для его загрузки.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-108">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="e0ad0-109">По умолчанию используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-109">The default is the name of the file name.</span></span>  
  
 <span data-ttu-id="e0ad0-110">`accessibility-modifier` (необязательно)</span><span class="sxs-lookup"><span data-stu-id="e0ad0-110">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="e0ad0-111">Доступность ресурса: "public" (открытый) или "private" (закрытый).</span><span class="sxs-lookup"><span data-stu-id="e0ad0-111">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="e0ad0-112">Значение по умолчанию — "public" (открытый).</span><span class="sxs-lookup"><span data-stu-id="e0ad0-112">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0ad0-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="e0ad0-113">Remarks</span></span>  
 <span data-ttu-id="e0ad0-114">С помощью параметра [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) можно связать ресурс со сборкой, в результате чего не потребуется добавлять файл ресурсов в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-114">Use [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) to link a resource to an assembly and not add the resource file to the output file.</span></span>  
  
 <span data-ttu-id="e0ad0-115">По умолчанию ресурсы в сборке открыты, если они создавались с помощью компилятора C#.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-115">By default, resources are public in the assembly when they are created by using the C# compiler.</span></span> <span data-ttu-id="e0ad0-116">Чтобы сделать ресурс закрытым, укажите параметр `private` в качестве модификатора доступа.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-116">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="e0ad0-117">Уровни доступности, отличные от `public` или `private`, не допускаются.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-117">No other accessibility other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="e0ad0-118">Если `filename` является файлом ресурсов .NET Framework, созданным, например, с помощью [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, то к нему можно обращаться с помощью членов пространства имен <xref:System.Resources>.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-118">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="e0ad0-119">Для получения дополнительной информации см. <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-119">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e0ad0-120">Другие ресурсы, используйте `GetManifestResource` методы в <xref:System.Reflection.Assembly> класса доступа к ресурсам во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-120">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="e0ad0-121">**/res** является краткой формой **/resource**.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-121">**/res** is the short form of **/resource**.</span></span>  
  
 <span data-ttu-id="e0ad0-122">Порядок расположения ресурсов в выходном файле будет определяться порядком, указанным в командной строке.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-122">The order of the resources in the output file is determined from the order specified on the command line.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e0ad0-123">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e0ad0-123">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="e0ad0-124">Добавьте файл ресурсов в проект.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-124">Add a resource file to your project.</span></span>  
  
2.  <span data-ttu-id="e0ad0-125">Выберите файл, который требуется внедрить, в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-125">Select the file that you want to embed in **Solution Explorer**.</span></span>  
  
3.  <span data-ttu-id="e0ad0-126">Выберите **Действие сборки** для файла в окне **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-126">Select **Build Action** for the file in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="e0ad0-127">Присвойте параметру **Действие сборки** значение **Внедренный ресурс**.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-127">Set **Build Action** to **Embedded Resource**.</span></span>  
  
 <span data-ttu-id="e0ad0-128">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0ad0-128">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0ad0-129">Пример</span><span class="sxs-lookup"><span data-stu-id="e0ad0-129">Example</span></span>  
 <span data-ttu-id="e0ad0-130">Компиляция `in.cs` и привязка файла ресурсов `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="e0ad0-130">Compile `in.cs` and attach resource file `rf.resource`:</span></span>  
  
```console  
csc /resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0ad0-131">См. также</span><span class="sxs-lookup"><span data-stu-id="e0ad0-131">See Also</span></span>  
 [<span data-ttu-id="e0ad0-132">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="e0ad0-132">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="e0ad0-133">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="e0ad0-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
