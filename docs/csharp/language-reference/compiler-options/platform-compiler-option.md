---
title: "-platform (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /platform
dev_langs:
- CSharp
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
caps.latest.revision: 46
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
ms.openlocfilehash: 44d4cadbc45eb141ecb7a83345d2a7a834ce5299
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="platform-c-compiler-options"></a><span data-ttu-id="ed99a-102">/platform (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="ed99a-102">/platform (C# Compiler Options)</span></span>
<span data-ttu-id="ed99a-103">Указывает, в какой версии среды CLR может запускаться сборка.</span><span class="sxs-lookup"><span data-stu-id="ed99a-103">Specifies which version of the common language runtime (CLR) can run the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed99a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed99a-104">Syntax</span></span>  
  
```console  
/platform:string  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed99a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed99a-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="ed99a-106">anycpu (по умолчанию), anycpu32bitpreferred, ARM, x64, x86 или Itanium.</span><span class="sxs-lookup"><span data-stu-id="ed99a-106">anycpu (default), anycpu32bitpreferred, ARM, x64, x86, or Itanium.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed99a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed99a-107">Remarks</span></span>  
  
-   <span data-ttu-id="ed99a-108">**anycpu** (по умолчанию) позволяет компилировать сборку для запуска на любой платформе.</span><span class="sxs-lookup"><span data-stu-id="ed99a-108">**anycpu** (default) compiles your assembly to run on any platform.</span></span> <span data-ttu-id="ed99a-109">Если возможно, приложение выполняется как 64-разрядный процесс, а если доступен только 32-разрядный режим, переключается на него.</span><span class="sxs-lookup"><span data-stu-id="ed99a-109">Your application runs as a 64-bit process whenever possible and falls back to 32-bit when only that mode is available.</span></span>  
  
-   <span data-ttu-id="ed99a-110">**anycpu32bitpreferred** (по умолчанию) позволяет компилировать сборку для запуска на любой платформе.</span><span class="sxs-lookup"><span data-stu-id="ed99a-110">**anycpu32bitpreferred** compiles your assembly to run on any platform.</span></span> <span data-ttu-id="ed99a-111">Приложение выполняется в 32-разрядном режиме в системах, поддерживающих и 64-разрядные, и 32-разрядные приложения.</span><span class="sxs-lookup"><span data-stu-id="ed99a-111">Your application runs in 32-bit mode on systems that support both 64-bit and 32-bit applications.</span></span> <span data-ttu-id="ed99a-112">Можно задать этот параметр только для проектов, предназначенных для среды .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="ed99a-112">You can specify this option only for projects that target the .NET Framework 4.5.</span></span>  
  
-   <span data-ttu-id="ed99a-113">**ARM** компилирует сборку для выполнения на компьютере с процессором Advanced RISC Machine (ARM).</span><span class="sxs-lookup"><span data-stu-id="ed99a-113">**ARM** compiles your assembly to run on a computer that has an Advanced RISC Machine (ARM) processor.</span></span>  
  
-   <span data-ttu-id="ed99a-114">**x64** компилирует сборку для работы в 64-разрядной среде CLR на компьютере, поддерживающем набор инструкций x64 или AMD64.</span><span class="sxs-lookup"><span data-stu-id="ed99a-114">**x64** compiles your assembly to be run by the 64-bit common language runtime on a computer that supports the AMD64 or EM64T instruction set.</span></span>  
  
-   <span data-ttu-id="ed99a-115">**x86** компилирует сборку для выполнения в 32-разрядной среде CLR, совместимой с архитектурой x86.</span><span class="sxs-lookup"><span data-stu-id="ed99a-115">**x86** compiles your assembly to be run by the 32-bit, x86-compatible common language runtime.</span></span>  
  
-   <span data-ttu-id="ed99a-116">**Itanium** компилирует сборку для выполнения в 64-разрядной среде CLR на компьютере с процессором Itanium.</span><span class="sxs-lookup"><span data-stu-id="ed99a-116">**Itanium** compiles your assembly to be run by the 64-bit common language runtime on a computer with an Itanium processor.</span></span>  
  
 <span data-ttu-id="ed99a-117">В 64-разрядной ОС Windows:</span><span class="sxs-lookup"><span data-stu-id="ed99a-117">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="ed99a-118">Сборки, скомпилированные с параметром **/platform:x86**, будут выполняться в 32-разрядной среде CLR с WOW64.</span><span class="sxs-lookup"><span data-stu-id="ed99a-118">Assemblies compiled with **/platform:x86** execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="ed99a-119">Библиотека DLL, скомпилированная с использованием параметра **/platform:anycpu**, выполняется в той же среде CLR, в которую загружается процесс.</span><span class="sxs-lookup"><span data-stu-id="ed99a-119">A DLL compiled with the **/platform:anycpu** executes on the same CLR as the process into which it is loaded.</span></span>  
  
-   <span data-ttu-id="ed99a-120">Исполняемые файлы, скомпилированные с использованием параметра **/platform:anycpu**, выполняются в 64-разрядной среде CLR.</span><span class="sxs-lookup"><span data-stu-id="ed99a-120">Executables that are compiled with the **/platform:anycpu** execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="ed99a-121">Исполняемые файлы, скомпилированные с использованием параметра **/platform:anycpu32bitpreferred**, выполняются в 32-разрядной среде CLR.</span><span class="sxs-lookup"><span data-stu-id="ed99a-121">Executables compiled with **/platform:anycpu32bitpreferred** execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="ed99a-122">Параметр **anycpu32bitpreferred** допустим только для исполняемых файлов (EXE-файлов), и для него необходима среда .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="ed99a-122">The **anycpu32bitpreferred** setting is valid only for executable (.EXE) files, and it requires the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="ed99a-123">Дополнительные сведения о разработке приложений для запуска в 64-разрядной операционной системе Windows см. в разделе [64-разрядные приложения](https://msdn.microsoft.com/library/ms241064).</span><span class="sxs-lookup"><span data-stu-id="ed99a-123">For more information about developing an application to run on a Windows 64-bit operating system, see [64-bit Applications](https://msdn.microsoft.com/library/ms241064).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ed99a-124">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ed99a-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="ed99a-125">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="ed99a-125">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="ed99a-126">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="ed99a-126">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="ed99a-127">Измените значение свойства **Целевая платформа**, а для проектов, предназначенных для среды .NET Framework 4.5, установите или снимите флажок **Предпочитать 32-разрядную**.</span><span class="sxs-lookup"><span data-stu-id="ed99a-127">Modify the **Platform target** property and, for projects that target the .NET Framework 4.5, select or clear the **Prefer 32-bit** check box.</span></span>  
  
 <span data-ttu-id="ed99a-128">Обратите внимание, что параметр **/platform** недоступен в среде разработки в Visual C# Express.</span><span class="sxs-lookup"><span data-stu-id="ed99a-128">**Note /platform** is not available in the development environment in Visual C# Express.</span></span>  
  
 <span data-ttu-id="ed99a-129">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span><span class="sxs-lookup"><span data-stu-id="ed99a-129">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed99a-130">Пример</span><span class="sxs-lookup"><span data-stu-id="ed99a-130">Example</span></span>  
 <span data-ttu-id="ed99a-131">В следующем примере показано использование параметра **/platform**, чтобы указать, что приложение должно выполняться в 64-разрядной среде CLR в 64-разрядной операционной системой Windows.</span><span class="sxs-lookup"><span data-stu-id="ed99a-131">The following example shows how to use the **/platform** option to specify that the application should be run by the 64-bit CLR on a 64-bit Windows operating system.</span></span>  
  
```console  
csc /platform:anycpu filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed99a-132">См. также</span><span class="sxs-lookup"><span data-stu-id="ed99a-132">See Also</span></span>  
 <span data-ttu-id="ed99a-133">[Параметры компилятора C#](index.md) </span><span class="sxs-lookup"><span data-stu-id="ed99a-133">[C# Compiler Options](index.md) </span></span>  
 [<span data-ttu-id="ed99a-134">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="ed99a-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

