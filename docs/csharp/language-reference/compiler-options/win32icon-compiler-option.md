---
title: "-win32icon (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3f9419470d2f00a9f69aae24e925fea53d90cf10
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="win32icon-c-compiler-options"></a><span data-ttu-id="9b6bc-102">/win32icon (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="9b6bc-102">/win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="9b6bc-103">Параметр **/win32icon** вставляет в выходной файл ICO-файл, который придает выходному файлу необходимый вид в проводнике.</span><span class="sxs-lookup"><span data-stu-id="9b6bc-103">The **/win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b6bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b6bc-104">Syntax</span></span>  
  
```console  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="9b6bc-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9b6bc-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="9b6bc-106">ICO-файл, который требуется добавить в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="9b6bc-106">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b6bc-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b6bc-107">Remarks</span></span>  
 <span data-ttu-id="9b6bc-108">ICO-файл можно создать с помощью [компилятора ресурсов](http://go.microsoft.com/fwlink/?LinkId=148370).</span><span class="sxs-lookup"><span data-stu-id="9b6bc-108">An .ico file can be created with the [Resource Compiler](http://go.microsoft.com/fwlink/?LinkId=148370).</span></span> <span data-ttu-id="9b6bc-109">Компилятор ресурсов вызывается при компиляции программы Visual C++; ICO-файл создается из RC-файла.</span><span class="sxs-lookup"><span data-stu-id="9b6bc-109">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="9b6bc-110">Дополнительные сведения о ссылках на файлы ресурсов .NET Framework и их присоединении см. в разделах [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) и [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) соответственно.</span><span class="sxs-lookup"><span data-stu-id="9b6bc-110">See [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="9b6bc-111">Дополнительные сведения об импорте RES-файла см. в разделе [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="9b6bc-111">See [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="9b6bc-112">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9b6bc-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="9b6bc-113">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="9b6bc-113">Open the project's **Properties** pages.</span></span>  
  
2.  <span data-ttu-id="9b6bc-114">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="9b6bc-114">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="9b6bc-115">Измените свойство **Значок приложения**.</span><span class="sxs-lookup"><span data-stu-id="9b6bc-115">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="9b6bc-116">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="9b6bc-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b6bc-117">Пример</span><span class="sxs-lookup"><span data-stu-id="9b6bc-117">Example</span></span>  
 <span data-ttu-id="9b6bc-118">Скомпилируйте `in.cs` и присоедините ICO-файл `rf.ico`, чтобы получить файл `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="9b6bc-118">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc /win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b6bc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9b6bc-119">See Also</span></span>  
 [<span data-ttu-id="9b6bc-120">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="9b6bc-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="9b6bc-121">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="9b6bc-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
