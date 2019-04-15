---
title: -unsafe (параметры компилятора C#)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 4cfd7c82bc2cbf816164b235642c0647eeb7e5b6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337335"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="235cd-102">-unsafe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="235cd-102">-unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="235cd-103">Параметр **-unsafe** разрешает компилировать код, в котором используется ключевое слово [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="235cd-103">The **-unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="235cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="235cd-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="235cd-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="235cd-105">Remarks</span></span>  
 <span data-ttu-id="235cd-106">Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="235cd-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="235cd-107">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="235cd-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="235cd-108">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="235cd-108">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="235cd-109">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="235cd-109">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="235cd-110">Установите флажок **Разрешить небезопасный код**.</span><span class="sxs-lookup"><span data-stu-id="235cd-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="235cd-111">Добавление этого параметра в CSPROJ-файл</span><span class="sxs-lookup"><span data-stu-id="235cd-111">To add this option in a csproj file</span></span>

<span data-ttu-id="235cd-112">Откройте CSPROJ-файл проекта и добавьте следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="235cd-112">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="235cd-113">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="235cd-113">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="235cd-114">Пример</span><span class="sxs-lookup"><span data-stu-id="235cd-114">Example</span></span>  
 <span data-ttu-id="235cd-115">Скомпилируйте `in.cs` для небезопасного режима:</span><span class="sxs-lookup"><span data-stu-id="235cd-115">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="235cd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="235cd-116">See also</span></span>

- [<span data-ttu-id="235cd-117">Параметры компилятора C#</span><span class="sxs-lookup"><span data-stu-id="235cd-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="235cd-118">Управление свойствами проекта и решения</span><span class="sxs-lookup"><span data-stu-id="235cd-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
