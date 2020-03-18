---
title: -optimize (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /optimize
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
ms.openlocfilehash: bec99ca582070a99fd8b734ef8a7b9e71d945488
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606603"
---
# <a name="-optimize-c-compiler-options"></a><span data-ttu-id="fc876-102">-optimize (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="fc876-102">-optimize (C# Compiler Options)</span></span>
<span data-ttu-id="fc876-103">Параметр **-optimize** включает или отключает оптимизацию кода компилятором, чтобы сделать код более быстрым, коротким и эффективным.</span><span class="sxs-lookup"><span data-stu-id="fc876-103">The **-optimize** option enables or disables optimizations performed by the compiler to make your output file smaller, faster, and more efficient.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc876-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc876-104">Syntax</span></span>  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="fc876-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="fc876-105">Remarks</span></span>  
 <span data-ttu-id="fc876-106">Кроме того, параметр **-optimize** включает оптимизацию кода во время выполнения в общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="fc876-106">**-optimize** also tells the common language runtime to optimize code at runtime.</span></span>  
  
 <span data-ttu-id="fc876-107">По умолчанию оптимизация отключена.</span><span class="sxs-lookup"><span data-stu-id="fc876-107">By default, optimizations are disabled.</span></span> <span data-ttu-id="fc876-108">Чтобы включить оптимизацию, укажите **-optimize+** .</span><span class="sxs-lookup"><span data-stu-id="fc876-108">Specify **-optimize+** to enable optimizations.</span></span>  
  
 <span data-ttu-id="fc876-109">При создании модуля для сборки используйте те же настройки параметра **-optimize**, что и для сборки.</span><span class="sxs-lookup"><span data-stu-id="fc876-109">When building a module to be used by an assembly, use the same **-optimize** settings as those of the assembly.</span></span>  
  
 <span data-ttu-id="fc876-110">**-o** является краткой формой параметра **-optimize**.</span><span class="sxs-lookup"><span data-stu-id="fc876-110">**-o** is the short form of **-optimize**.</span></span>  
  
 <span data-ttu-id="fc876-111">Параметры **-optimize** и [-debug](./debug-compiler-option.md) можно объединять.</span><span class="sxs-lookup"><span data-stu-id="fc876-111">It is possible to combine the **-optimize** and [-debug](./debug-compiler-option.md) options.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="fc876-112">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fc876-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="fc876-113">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="fc876-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="fc876-114">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="fc876-114">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="fc876-115">Измените свойство **Оптимизировать код**.</span><span class="sxs-lookup"><span data-stu-id="fc876-115">Modify the **Optimize Code** property.</span></span>  
  
 <span data-ttu-id="fc876-116">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc876-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc876-117">Пример</span><span class="sxs-lookup"><span data-stu-id="fc876-117">Example</span></span>  
 <span data-ttu-id="fc876-118">Скомпилируйте `t2.cs` и включите выполняемую компилятором оптимизацию:</span><span class="sxs-lookup"><span data-stu-id="fc876-118">Compile `t2.cs` and enable compiler optimizations:</span></span>  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc876-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fc876-119">See also</span></span>

- [<span data-ttu-id="fc876-120">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="fc876-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="fc876-121">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="fc876-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
