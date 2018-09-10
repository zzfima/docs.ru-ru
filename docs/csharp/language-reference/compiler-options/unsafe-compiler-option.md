---
title: -unsafe (параметры компилятора C#)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 138c7cce83fd069f44025c57e52b2d01bcb23432
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518054"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="c497e-102">-unsafe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="c497e-102">-unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="c497e-103">Параметр **-unsafe** разрешает компилировать код, в котором используется ключевое слово [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="c497e-103">The **-unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c497e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c497e-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="c497e-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="c497e-105">Remarks</span></span>  
 <span data-ttu-id="c497e-106">Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="c497e-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="c497e-107">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c497e-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="c497e-108">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="c497e-108">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="c497e-109">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="c497e-109">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="c497e-110">Установите флажок **Разрешить небезопасный код**.</span><span class="sxs-lookup"><span data-stu-id="c497e-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="c497e-111">Добавление этого параметра в CSPROJ-файл</span><span class="sxs-lookup"><span data-stu-id="c497e-111">To add this option in a csproj file</span></span>

<span data-ttu-id="c497e-112">Откройте CSPROJ-файл проекта и добавьте следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="c497e-112">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="c497e-113">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="c497e-113">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c497e-114">Пример</span><span class="sxs-lookup"><span data-stu-id="c497e-114">Example</span></span>  
 <span data-ttu-id="c497e-115">Скомпилируйте `in.cs` для небезопасного режима:</span><span class="sxs-lookup"><span data-stu-id="c497e-115">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="c497e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c497e-116">See Also</span></span>  

- [<span data-ttu-id="c497e-117">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="c497e-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="c497e-118">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="c497e-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
