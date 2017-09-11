---
title: "-nowarn (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nowarn
dev_langs:
- CSharp
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
caps.latest.revision: 24
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
ms.openlocfilehash: 3bae7e6d16c044b8f1aeba26de434cdf17479e82
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="nowarn-c-compiler-options"></a><span data-ttu-id="e922a-102">/nowarn (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="e922a-102">/nowarn (C# Compiler Options)</span></span>
<span data-ttu-id="e922a-103">Параметр **/nowarn** позволяет предотвратить отображение одного или нескольких предупреждений компилятором.</span><span class="sxs-lookup"><span data-stu-id="e922a-103">The **/nowarn** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="e922a-104">Разделяйте предупреждения запятыми.</span><span class="sxs-lookup"><span data-stu-id="e922a-104">Separate multiple warning numbers with a comma.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e922a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e922a-105">Syntax</span></span>  
  
```console  
/nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e922a-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e922a-106">Arguments</span></span>  
 <span data-ttu-id="e922a-107">`number1`, `number2`</span><span class="sxs-lookup"><span data-stu-id="e922a-107">`number1`, `number2`</span></span>  
 <span data-ttu-id="e922a-108">Номер (номера) предупреждений, которые требуется отключить в компиляторе.</span><span class="sxs-lookup"><span data-stu-id="e922a-108">Warning number(s) that you want the compiler to suppress.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e922a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="e922a-109">Remarks</span></span>  
 <span data-ttu-id="e922a-110">Необходимо указать только числовую часть идентификатора предупреждения.</span><span class="sxs-lookup"><span data-stu-id="e922a-110">You should only specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="e922a-111">Например, если требуется отключить CS0028, можно указать `/nowarn:28`.</span><span class="sxs-lookup"><span data-stu-id="e922a-111">For example, if you want to suppress CS0028, you could specify `/nowarn:28`.</span></span>  
  
 <span data-ttu-id="e922a-112">Компилятор просто пропустит номера предупреждений, переданные `/nowarn`, которые использовались в предыдущих версиях, но были удалены из компилятора.</span><span class="sxs-lookup"><span data-stu-id="e922a-112">The compiler will silently ignore warning numbers passed to `/nowarn` that were valid in previous releases, but that have been removed from the compiler.</span></span> <span data-ttu-id="e922a-113">Например, предупреждение CS0679 использовалось в компиляторе Visual Studio .NET 2002, но было удалено в последующих версиях.</span><span class="sxs-lookup"><span data-stu-id="e922a-113">For example, CS0679 was valid in the compiler in Visual Studio .NET 2002 but was subsequently removed.</span></span>  
  
 <span data-ttu-id="e922a-114">Параметр `/nowarn` позволяет отключить следующие предупреждения:</span><span class="sxs-lookup"><span data-stu-id="e922a-114">The following warnings cannot be suppressed by the `/nowarn` option:</span></span>  
  
-   <span data-ttu-id="e922a-115">Предупреждение компилятора (уровень 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="e922a-115">Compiler Warning (level 1) CS2002</span></span>  
  
-   <span data-ttu-id="e922a-116">Предупреждение компилятора (уровень 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="e922a-116">Compiler Warning (level 1) CS2023</span></span>  
  
-   <span data-ttu-id="e922a-117">Предупреждение компилятора (уровень 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="e922a-117">Compiler Warning (level 1) CS2029</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e922a-118">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e922a-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="e922a-119">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="e922a-119">Open the **Properties** page for the project.</span></span> <span data-ttu-id="e922a-120">Дополнительные сведения см. в разделе [Страница "Сборка", конструктор проектов (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="e922a-120">For details, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="e922a-121">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="e922a-121">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="e922a-122">Измените свойство **Отключить предупреждения**.</span><span class="sxs-lookup"><span data-stu-id="e922a-122">Modify the **Suppress Warnings** property.</span></span>  
  
 <span data-ttu-id="e922a-123">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="e922a-123">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e922a-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e922a-124">See Also</span></span>  
 <span data-ttu-id="e922a-125">[Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="e922a-125">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="e922a-126">[Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties) </span><span class="sxs-lookup"><span data-stu-id="e922a-126">[Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties) </span></span>  
 [<span data-ttu-id="e922a-127">Ошибки компилятора C#</span><span class="sxs-lookup"><span data-stu-id="e922a-127">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)

