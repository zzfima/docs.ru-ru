---
title: "-unsafe (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.assetid: fdb77ed9-da03-45bd-bb7f-250704da1bcc
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b253a9ddafead823480f9893e809f17b6c22a179
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="1f46a-102">-unsafe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="1f46a-102">-unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="1f46a-103">Параметр **-unsafe** разрешает компилировать код, в котором используется ключевое слово [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="1f46a-103">The **-unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f46a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f46a-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="1f46a-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f46a-105">Remarks</span></span>  
 <span data-ttu-id="1f46a-106">Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="1f46a-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="1f46a-107">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1f46a-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="1f46a-108">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="1f46a-108">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="1f46a-109">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="1f46a-109">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="1f46a-110">Установите флажок **Разрешить небезопасный код**.</span><span class="sxs-lookup"><span data-stu-id="1f46a-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
 <span data-ttu-id="1f46a-111">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="1f46a-111">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f46a-112">Пример</span><span class="sxs-lookup"><span data-stu-id="1f46a-112">Example</span></span>  
 <span data-ttu-id="1f46a-113">Скомпилируйте `in.cs` для небезопасного режима:</span><span class="sxs-lookup"><span data-stu-id="1f46a-113">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f46a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1f46a-114">See Also</span></span>  
 [<span data-ttu-id="1f46a-115">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="1f46a-115">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="1f46a-116">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="1f46a-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
