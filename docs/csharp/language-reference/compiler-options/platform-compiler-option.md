---
title: -platform (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /platform
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
ms.openlocfilehash: 1573e28f2a6f9dec7825d364debcdf1085ef7ff2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635671"
---
# <a name="-platform-c-compiler-options"></a><span data-ttu-id="947b8-102">-platform (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="947b8-102">-platform (C# Compiler Options)</span></span>
<span data-ttu-id="947b8-103">Указывает, в какой версии среды CLR может запускаться сборка.</span><span class="sxs-lookup"><span data-stu-id="947b8-103">Specifies which version of the Common Language Runtime (CLR) can run the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="947b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="947b8-104">Syntax</span></span>  
  
```console  
-platform:string  
```  
  
#### <a name="parameters"></a><span data-ttu-id="947b8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="947b8-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="947b8-106">anycpu (по умолчанию), anycpu32bitpreferred, ARM, x64, x86 или Itanium.</span><span class="sxs-lookup"><span data-stu-id="947b8-106">anycpu (default), anycpu32bitpreferred, ARM, x64, x86, or Itanium.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="947b8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="947b8-107">Remarks</span></span>  
  
-   <span data-ttu-id="947b8-108">**anycpu** (по умолчанию) позволяет компилировать сборку для запуска на любой платформе.</span><span class="sxs-lookup"><span data-stu-id="947b8-108">**anycpu** (default) compiles your assembly to run on any platform.</span></span> <span data-ttu-id="947b8-109">Если возможно, приложение выполняется как 64-разрядный процесс, а если доступен только 32-разрядный режим, переключается на него.</span><span class="sxs-lookup"><span data-stu-id="947b8-109">Your application runs as a 64-bit process whenever possible and falls back to 32-bit when only that mode is available.</span></span>  
  
-   <span data-ttu-id="947b8-110">**anycpu32bitpreferred** (по умолчанию) позволяет компилировать сборку для запуска на любой платформе.</span><span class="sxs-lookup"><span data-stu-id="947b8-110">**anycpu32bitpreferred** compiles your assembly to run on any platform.</span></span> <span data-ttu-id="947b8-111">Приложение выполняется в 32-разрядном режиме в системах, поддерживающих и 64-разрядные, и 32-разрядные приложения.</span><span class="sxs-lookup"><span data-stu-id="947b8-111">Your application runs in 32-bit mode on systems that support both 64-bit and 32-bit applications.</span></span> <span data-ttu-id="947b8-112">Можно задать этот параметр только для проектов, предназначенных для среды .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="947b8-112">You can specify this option only for projects that target the .NET Framework 4.5.</span></span>  
  
-   <span data-ttu-id="947b8-113">**ARM** компилирует сборку для выполнения на компьютере с процессором Advanced RISC Machine (ARM).</span><span class="sxs-lookup"><span data-stu-id="947b8-113">**ARM** compiles your assembly to run on a computer that has an Advanced RISC Machine (ARM) processor.</span></span>  
  
-   <span data-ttu-id="947b8-114">**x64** компилирует сборку для запуска в 64-разрядной среде CLR на компьютере, поддерживающем набор инструкций AMD64 или EM64T.</span><span class="sxs-lookup"><span data-stu-id="947b8-114">**x64** compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>  
  
-   <span data-ttu-id="947b8-115">**x86** компилирует сборку для запуска в 32-разрядной среде CLR с архитектурой x86.</span><span class="sxs-lookup"><span data-stu-id="947b8-115">**x86** compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>  
  
-   <span data-ttu-id="947b8-116">**Itanium** компилирует сборку для запуска в 64-разрядной среде CLR на компьютере с процессором Itanium.</span><span class="sxs-lookup"><span data-stu-id="947b8-116">**Itanium** compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>  
  
 <span data-ttu-id="947b8-117">В 64-разрядной ОС Windows:</span><span class="sxs-lookup"><span data-stu-id="947b8-117">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="947b8-118">Сборки, скомпилированные с параметром **-platform:x86**, будут выполняться в 32-разрядной среде CLR с WOW64.</span><span class="sxs-lookup"><span data-stu-id="947b8-118">Assemblies compiled with **-platform:x86** execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="947b8-119">Библиотека DLL, скомпилированная с использованием параметра **-platform:anycpu**, выполняется в той же среде CLR, в которую загружается процесс.</span><span class="sxs-lookup"><span data-stu-id="947b8-119">A DLL compiled with the **-platform:anycpu** executes on the same CLR as the process into which it is loaded.</span></span>  
  
-   <span data-ttu-id="947b8-120">Исполняемые файлы, скомпилированные с использованием параметра **-platform:anycpu**, выполняются в 64-разрядной среде CLR.</span><span class="sxs-lookup"><span data-stu-id="947b8-120">Executables that are compiled with the **-platform:anycpu** execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="947b8-121">Исполняемые файлы, скомпилированные с использованием параметра **-platform:anycpu32bitpreferred**, выполняются в 32-разрядной среде CLR.</span><span class="sxs-lookup"><span data-stu-id="947b8-121">Executables compiled with **-platform:anycpu32bitpreferred** execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="947b8-122">Параметр **anycpu32bitpreferred** допустим только для исполняемых файлов (EXE-файлов), и для него необходима среда .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="947b8-122">The **anycpu32bitpreferred** setting is valid only for executable (.EXE) files, and it requires the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="947b8-123">Дополнительные сведения о разработке приложений для запуска в 64-разрядной операционной системе Windows см. в разделе [64-разрядные приложения](../../../framework/64-bit-apps.md).</span><span class="sxs-lookup"><span data-stu-id="947b8-123">For more information about developing an application to run on a Windows 64-bit operating system, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="947b8-124">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="947b8-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="947b8-125">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="947b8-125">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="947b8-126">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="947b8-126">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="947b8-127">Измените значение свойства **Целевая платформа**, а для проектов, предназначенных для среды .NET Framework 4.5, установите или снимите флажок **Предпочитать 32-разрядную**.</span><span class="sxs-lookup"><span data-stu-id="947b8-127">Modify the **Platform target** property and, for projects that target the .NET Framework 4.5, select or clear the **Prefer 32-bit** check box.</span></span>  
  
 <span data-ttu-id="947b8-128">Обратите внимание, что параметр **-platform** недоступен в среде разработки в Visual C# Express.</span><span class="sxs-lookup"><span data-stu-id="947b8-128">**Note -platform** is not available in the development environment in Visual C# Express.</span></span>  
  
 <span data-ttu-id="947b8-129">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span><span class="sxs-lookup"><span data-stu-id="947b8-129">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="947b8-130">Пример</span><span class="sxs-lookup"><span data-stu-id="947b8-130">Example</span></span>  
 <span data-ttu-id="947b8-131">В следующем примере показано использование параметра **-platform**, чтобы указать, что приложение должно выполняться в 64-разрядной среде CLR в 64-разрядной операционной системой Windows.</span><span class="sxs-lookup"><span data-stu-id="947b8-131">The following example shows how to use the **-platform** option to specify that the application should be run by the 64-bit CLR on a 64-bit Windows operating system.</span></span>  
  
```console  
csc -platform:anycpu filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="947b8-132">См. также</span><span class="sxs-lookup"><span data-stu-id="947b8-132">See also</span></span>

- [<span data-ttu-id="947b8-133">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="947b8-133">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="947b8-134">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="947b8-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
