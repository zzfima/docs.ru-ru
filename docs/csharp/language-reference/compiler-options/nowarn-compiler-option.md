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
ms.openlocfilehash: fa3079bf1431ba1a16b5a2eef0dd5500fe95909c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606613"
---
# <a name="-nowarn-c-compiler-options"></a><span data-ttu-id="f70c7-102">-nowarn (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="f70c7-102">-nowarn (C# Compiler Options)</span></span>
<span data-ttu-id="f70c7-103">Параметр **-nowarn** позволяет предотвратить отображение одного или нескольких предупреждений компилятором.</span><span class="sxs-lookup"><span data-stu-id="f70c7-103">The **-nowarn** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="f70c7-104">Разделяйте предупреждения запятыми.</span><span class="sxs-lookup"><span data-stu-id="f70c7-104">Separate multiple warning numbers with a comma.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f70c7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f70c7-105">Syntax</span></span>  
  
```console  
-nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f70c7-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f70c7-106">Arguments</span></span>  
 <span data-ttu-id="f70c7-107">`number1`, `number2`</span><span class="sxs-lookup"><span data-stu-id="f70c7-107">`number1`, `number2`</span></span>  
 <span data-ttu-id="f70c7-108">Номер (номера) предупреждений, которые требуется отключить в компиляторе.</span><span class="sxs-lookup"><span data-stu-id="f70c7-108">Warning number(s) that you want the compiler to suppress.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f70c7-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f70c7-109">Remarks</span></span>  
 <span data-ttu-id="f70c7-110">Необходимо указать только числовую часть идентификатора предупреждения.</span><span class="sxs-lookup"><span data-stu-id="f70c7-110">You should only specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="f70c7-111">Например, если требуется отключить CS0028, можно указать `-nowarn:28`.</span><span class="sxs-lookup"><span data-stu-id="f70c7-111">For example, if you want to suppress CS0028, you could specify `-nowarn:28`.</span></span>  
  
 <span data-ttu-id="f70c7-112">Компилятор просто пропустит номера предупреждений, переданные `-nowarn`, которые использовались в предыдущих версиях, но были удалены из компилятора.</span><span class="sxs-lookup"><span data-stu-id="f70c7-112">The compiler will silently ignore warning numbers passed to `-nowarn` that were valid in previous releases, but that have been removed from the compiler.</span></span> <span data-ttu-id="f70c7-113">Например, предупреждение CS0679 использовалось в компиляторе Visual Studio .NET 2002, но было удалено в последующих версиях.</span><span class="sxs-lookup"><span data-stu-id="f70c7-113">For example, CS0679 was valid in the compiler in Visual Studio .NET 2002 but was subsequently removed.</span></span>  
  
 <span data-ttu-id="f70c7-114">Параметр `-nowarn` позволяет отключить следующие предупреждения:</span><span class="sxs-lookup"><span data-stu-id="f70c7-114">The following warnings cannot be suppressed by the `-nowarn` option:</span></span>  
  
- <span data-ttu-id="f70c7-115">Предупреждение компилятора (уровень 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="f70c7-115">Compiler Warning (level 1) CS2002</span></span>  
  
- <span data-ttu-id="f70c7-116">Предупреждение компилятора (уровень 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="f70c7-116">Compiler Warning (level 1) CS2023</span></span>  
  
- <span data-ttu-id="f70c7-117">Предупреждение компилятора (уровень 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="f70c7-117">Compiler Warning (level 1) CS2029</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f70c7-118">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f70c7-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="f70c7-119">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="f70c7-119">Open the **Properties** page for the project.</span></span> <span data-ttu-id="f70c7-120">Дополнительные сведения см. в разделе [Страница "Сборка", конструктор проектов (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="f70c7-120">For details, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="f70c7-121">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="f70c7-121">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="f70c7-122">Измените свойство **Отключить предупреждения**.</span><span class="sxs-lookup"><span data-stu-id="f70c7-122">Modify the **Suppress Warnings** property.</span></span>  
  
 <span data-ttu-id="f70c7-123">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="f70c7-123">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f70c7-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f70c7-124">See also</span></span>

- [<span data-ttu-id="f70c7-125">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="f70c7-125">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="f70c7-126">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="f70c7-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="f70c7-127">Ошибки компилятора C#</span><span class="sxs-lookup"><span data-stu-id="f70c7-127">C# Compiler Errors</span></span>](../compiler-messages/index.md)
