---
title: -win32icon (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: f3df92d8d0b0135eac1a055afafffa0015fecc2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606278"
---
# <a name="-win32icon-c-compiler-options"></a><span data-ttu-id="d5aa3-102">-win32icon (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="d5aa3-102">-win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="d5aa3-103">Параметр **-win32icon** вставляет в выходной файл ICO-файл, который придает выходному файлу необходимый вид в проводнике.</span><span class="sxs-lookup"><span data-stu-id="d5aa3-103">The **-win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5aa3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5aa3-104">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="d5aa3-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d5aa3-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="d5aa3-106">ICO-файл, который требуется добавить в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="d5aa3-106">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5aa3-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5aa3-107">Remarks</span></span>  
 <span data-ttu-id="d5aa3-108">ICO-файл можно создать с помощью [компилятора ресурсов](/windows/desktop/menurc/resource-compiler).</span><span class="sxs-lookup"><span data-stu-id="d5aa3-108">An .ico file can be created with the [Resource Compiler](/windows/desktop/menurc/resource-compiler).</span></span> <span data-ttu-id="d5aa3-109">Компилятор ресурсов вызывается при компиляции программы Visual C++; ICO-файл создается из RC-файла.</span><span class="sxs-lookup"><span data-stu-id="d5aa3-109">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="d5aa3-110">Дополнительные сведения о ссылках на файлы ресурсов .NET Framework и их присоединении см. в разделах [-linkresource](./linkresource-compiler-option.md) и [-resource](./resource-compiler-option.md) соответственно.</span><span class="sxs-lookup"><span data-stu-id="d5aa3-110">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="d5aa3-111">Дополнительные сведения об импорте RES-файла см. в разделе [-win32res](./win32res-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="d5aa3-111">See [-win32res](./win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="d5aa3-112">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d5aa3-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="d5aa3-113">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="d5aa3-113">Open the project's **Properties** pages.</span></span>  
  
2. <span data-ttu-id="d5aa3-114">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="d5aa3-114">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="d5aa3-115">Измените свойство **Значок приложения**.</span><span class="sxs-lookup"><span data-stu-id="d5aa3-115">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="d5aa3-116">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5aa3-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5aa3-117">Пример</span><span class="sxs-lookup"><span data-stu-id="d5aa3-117">Example</span></span>  
 <span data-ttu-id="d5aa3-118">Скомпилируйте `in.cs` и присоедините ICO-файл `rf.ico`, чтобы получить файл `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="d5aa3-118">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5aa3-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d5aa3-119">See also</span></span>

- [<span data-ttu-id="d5aa3-120">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="d5aa3-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="d5aa3-121">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="d5aa3-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
