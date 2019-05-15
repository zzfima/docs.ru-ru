---
title: -nowarn (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /nowarn
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
ms.openlocfilehash: b455a2f719e7350c51cf4a1f095d4669529d0e5e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592809"
---
# <a name="-nowarn-c-compiler-options"></a><span data-ttu-id="aeadd-102">-nowarn (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="aeadd-102">-nowarn (C# Compiler Options)</span></span>
<span data-ttu-id="aeadd-103">Параметр **-nowarn** позволяет предотвратить отображение одного или нескольких предупреждений компилятором.</span><span class="sxs-lookup"><span data-stu-id="aeadd-103">The **-nowarn** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="aeadd-104">Разделяйте предупреждения запятыми.</span><span class="sxs-lookup"><span data-stu-id="aeadd-104">Separate multiple warning numbers with a comma.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aeadd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aeadd-105">Syntax</span></span>  
  
```console  
-nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a><span data-ttu-id="aeadd-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="aeadd-106">Arguments</span></span>  
 <span data-ttu-id="aeadd-107">`number1`, `number2`</span><span class="sxs-lookup"><span data-stu-id="aeadd-107">`number1`, `number2`</span></span>  
 <span data-ttu-id="aeadd-108">Номер (номера) предупреждений, которые требуется отключить в компиляторе.</span><span class="sxs-lookup"><span data-stu-id="aeadd-108">Warning number(s) that you want the compiler to suppress.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aeadd-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="aeadd-109">Remarks</span></span>  
 <span data-ttu-id="aeadd-110">Необходимо указать только числовую часть идентификатора предупреждения.</span><span class="sxs-lookup"><span data-stu-id="aeadd-110">You should only specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="aeadd-111">Например, если требуется отключить CS0028, можно указать `-nowarn:28`.</span><span class="sxs-lookup"><span data-stu-id="aeadd-111">For example, if you want to suppress CS0028, you could specify `-nowarn:28`.</span></span>  
  
 <span data-ttu-id="aeadd-112">Компилятор просто пропустит номера предупреждений, переданные `-nowarn`, которые использовались в предыдущих версиях, но были удалены из компилятора.</span><span class="sxs-lookup"><span data-stu-id="aeadd-112">The compiler will silently ignore warning numbers passed to `-nowarn` that were valid in previous releases, but that have been removed from the compiler.</span></span> <span data-ttu-id="aeadd-113">Например, предупреждение CS0679 использовалось в компиляторе Visual Studio .NET 2002, но было удалено в последующих версиях.</span><span class="sxs-lookup"><span data-stu-id="aeadd-113">For example, CS0679 was valid in the compiler in Visual Studio .NET 2002 but was subsequently removed.</span></span>  
  
 <span data-ttu-id="aeadd-114">Параметр `-nowarn` позволяет отключить следующие предупреждения:</span><span class="sxs-lookup"><span data-stu-id="aeadd-114">The following warnings cannot be suppressed by the `-nowarn` option:</span></span>  
  
- <span data-ttu-id="aeadd-115">Предупреждение компилятора (уровень 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="aeadd-115">Compiler Warning (level 1) CS2002</span></span>  
  
- <span data-ttu-id="aeadd-116">Предупреждение компилятора (уровень 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="aeadd-116">Compiler Warning (level 1) CS2023</span></span>  
  
- <span data-ttu-id="aeadd-117">Предупреждение компилятора (уровень 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="aeadd-117">Compiler Warning (level 1) CS2029</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="aeadd-118">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aeadd-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="aeadd-119">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="aeadd-119">Open the **Properties** page for the project.</span></span> <span data-ttu-id="aeadd-120">Дополнительные сведения см. в разделе [Страница "Сборка", конструктор проектов (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="aeadd-120">For details, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="aeadd-121">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="aeadd-121">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="aeadd-122">Измените свойство **Отключить предупреждения**.</span><span class="sxs-lookup"><span data-stu-id="aeadd-122">Modify the **Suppress Warnings** property.</span></span>  
  
 <span data-ttu-id="aeadd-123">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="aeadd-123">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeadd-124">См. также</span><span class="sxs-lookup"><span data-stu-id="aeadd-124">See also</span></span>

- [<span data-ttu-id="aeadd-125">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="aeadd-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="aeadd-126">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="aeadd-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="aeadd-127">Ошибки компилятора C#</span><span class="sxs-lookup"><span data-stu-id="aeadd-127">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)
