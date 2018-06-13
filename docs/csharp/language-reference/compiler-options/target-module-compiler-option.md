---
title: -target:module (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: d02a46390ca34b8063320df6ec237a00c0423c88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214258"
---
# <a name="-targetmodule-c-compiler-options"></a><span data-ttu-id="f8efa-102">-target:module (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="f8efa-102">-target:module (C# Compiler Options)</span></span>
<span data-ttu-id="f8efa-103">Этот параметр указывает компилятору не создавать манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="f8efa-103">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8efa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8efa-104">Syntax</span></span>  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="f8efa-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8efa-105">Remarks</span></span>  
 <span data-ttu-id="f8efa-106">По умолчанию выходной файл, созданный при компиляции с этим параметром, имеет расширение .netmodule.</span><span class="sxs-lookup"><span data-stu-id="f8efa-106">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="f8efa-107">Файл без манифеста сборки не может быть загружен в общеязыковую среду выполнения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f8efa-107">A file that does not have an assembly manifest cannot be loaded by the .NET Framework common language runtime.</span></span> <span data-ttu-id="f8efa-108">Тем не менее его можно включить в манифест сборки с помощью параметра [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f8efa-108">However, such a file can be incorporated into the assembly manifest of an assembly by means of [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="f8efa-109">Если в рамках одной процедуры компиляции создается несколько модулей, типы [internal](../../../csharp/language-reference/keywords/internal.md) из одного модуля будут доступны для других модулей, компилируемых вместе с ним.</span><span class="sxs-lookup"><span data-stu-id="f8efa-109">If more than one module is created in a single compilation, [internal](../../../csharp/language-reference/keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="f8efa-110">Если код одного модуля ссылается на типы `internal` в другом модуле, оба модуля нужно включить в манифест сборки с помощью параметра **-addmodule**.</span><span class="sxs-lookup"><span data-stu-id="f8efa-110">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **-addmodule**.</span></span>  
  
 <span data-ttu-id="f8efa-111">Создание модуля в среде разработки Visual Studio не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f8efa-111">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="f8efa-112">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="f8efa-112">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8efa-113">Пример</span><span class="sxs-lookup"><span data-stu-id="f8efa-113">Example</span></span>  
 <span data-ttu-id="f8efa-114">Компиляция файла`in.cs`, создание модуля `in.netmodule`:</span><span class="sxs-lookup"><span data-stu-id="f8efa-114">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8efa-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f8efa-115">See Also</span></span>  
 [<span data-ttu-id="f8efa-116">-target (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="f8efa-116">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="f8efa-117">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="f8efa-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
