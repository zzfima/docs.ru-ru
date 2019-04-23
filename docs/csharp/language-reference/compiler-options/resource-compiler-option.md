---
title: -resource (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: ed9f4648ae632786ce860ce2c02637977f709c55
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59302573"
---
# <a name="-resource-c-compiler-options"></a><span data-ttu-id="582fc-102">-resource (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="582fc-102">-resource (C# Compiler Options)</span></span>
<span data-ttu-id="582fc-103">Внедряет указанный ресурс в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="582fc-103">Embeds the specified resource into the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="582fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="582fc-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="582fc-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="582fc-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="582fc-106">Файл ресурсов платформы .NET Framework, который требуется внедрить в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="582fc-106">The .NET Framework resource file that you want to embed in the output file.</span></span>  
  
 <span data-ttu-id="582fc-107">`identifier` (необязательно)</span><span class="sxs-lookup"><span data-stu-id="582fc-107">`identifier` (optional)</span></span>  
 <span data-ttu-id="582fc-108">Логическое имя ресурса, используемое для его загрузки.</span><span class="sxs-lookup"><span data-stu-id="582fc-108">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="582fc-109">По умолчанию используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="582fc-109">The default is the name of the file name.</span></span>  
  
 <span data-ttu-id="582fc-110">`accessibility-modifier` (необязательно)</span><span class="sxs-lookup"><span data-stu-id="582fc-110">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="582fc-111">Доступность ресурса: "public" (открытый) или "private" (закрытый).</span><span class="sxs-lookup"><span data-stu-id="582fc-111">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="582fc-112">Значение по умолчанию — "public" (открытый).</span><span class="sxs-lookup"><span data-stu-id="582fc-112">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="582fc-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="582fc-113">Remarks</span></span>  
 <span data-ttu-id="582fc-114">Используйте [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md), чтобы связать ресурс со сборкой и не добавлять файл ресурсов в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="582fc-114">Use [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) to link a resource to an assembly and not add the resource file to the output file.</span></span>  
  
 <span data-ttu-id="582fc-115">По умолчанию ресурсы в сборке открыты, если они создавались с помощью компилятора C#.</span><span class="sxs-lookup"><span data-stu-id="582fc-115">By default, resources are public in the assembly when they are created by using the C# compiler.</span></span> <span data-ttu-id="582fc-116">Чтобы сделать ресурс закрытым, укажите параметр `private` в качестве модификатора доступа.</span><span class="sxs-lookup"><span data-stu-id="582fc-116">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="582fc-117">Уровни доступности, отличные от `public` или `private`, не допускаются.</span><span class="sxs-lookup"><span data-stu-id="582fc-117">No other accessibility other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="582fc-118">Если `filename` является файлом ресурсов .NET Framework, созданным, например, с помощью [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, то к нему можно обращаться с помощью членов пространства имен <xref:System.Resources>.</span><span class="sxs-lookup"><span data-stu-id="582fc-118">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="582fc-119">Для получения дополнительной информации см. <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="582fc-119">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="582fc-120">Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте методы `GetManifestResource` в классе <xref:System.Reflection.Assembly>.</span><span class="sxs-lookup"><span data-stu-id="582fc-120">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="582fc-121">**-res** является краткой формой **-resource**.</span><span class="sxs-lookup"><span data-stu-id="582fc-121">**-res** is the short form of **-resource**.</span></span>  
  
 <span data-ttu-id="582fc-122">Порядок расположения ресурсов в выходном файле будет определяться порядком, указанным в командной строке.</span><span class="sxs-lookup"><span data-stu-id="582fc-122">The order of the resources in the output file is determined from the order specified on the command line.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="582fc-123">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="582fc-123">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="582fc-124">Добавьте файл ресурсов в проект.</span><span class="sxs-lookup"><span data-stu-id="582fc-124">Add a resource file to your project.</span></span>  
  
2. <span data-ttu-id="582fc-125">Выберите файл, который требуется внедрить, в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="582fc-125">Select the file that you want to embed in **Solution Explorer**.</span></span>  
  
3. <span data-ttu-id="582fc-126">Выберите **Действие сборки** для файла в окне **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="582fc-126">Select **Build Action** for the file in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="582fc-127">Присвойте параметру **Действие сборки** значение **Внедренный ресурс**.</span><span class="sxs-lookup"><span data-stu-id="582fc-127">Set **Build Action** to **Embedded Resource**.</span></span>  
  
 <span data-ttu-id="582fc-128">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span><span class="sxs-lookup"><span data-stu-id="582fc-128">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="582fc-129">Пример</span><span class="sxs-lookup"><span data-stu-id="582fc-129">Example</span></span>  
 <span data-ttu-id="582fc-130">Компиляция `in.cs` и привязка файла ресурсов `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="582fc-130">Compile `in.cs` and attach resource file `rf.resource`:</span></span>  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="582fc-131">См. также</span><span class="sxs-lookup"><span data-stu-id="582fc-131">See also</span></span>

- [<span data-ttu-id="582fc-132">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="582fc-132">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="582fc-133">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="582fc-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
