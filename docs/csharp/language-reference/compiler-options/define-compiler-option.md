---
title: -define (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /define
helpviewer_keywords:
- -define compiler option [C#]
- /define compiler option [C#]
- -d compiler option [C#]
- define compiler option [C#]
- /d compiler option [C#]
- d compiler option [C#]
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
ms.openlocfilehash: 4a3622b6acc8ebe9c590b01b67074ae59396fc34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173748"
---
# <a name="-define-c-compiler-options"></a><span data-ttu-id="71862-102">-define (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="71862-102">-define (C# Compiler Options)</span></span>
<span data-ttu-id="71862-103">Параметр **-define** определяет `name` как символ во всех файлах исходного кода программы.</span><span class="sxs-lookup"><span data-stu-id="71862-103">The **-define** option defines `name` as a symbol in all source code files your program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71862-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71862-104">Syntax</span></span>  
  
```console  
-define:name[;name2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="71862-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="71862-105">Arguments</span></span>  
 <span data-ttu-id="71862-106">`name`, `name2`</span><span class="sxs-lookup"><span data-stu-id="71862-106">`name`, `name2`</span></span>  
 <span data-ttu-id="71862-107">Имя одного или нескольких символов, которые требуется определить.</span><span class="sxs-lookup"><span data-stu-id="71862-107">The name of one or more symbols that you want to define.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71862-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="71862-108">Remarks</span></span>  
 <span data-ttu-id="71862-109">Параметр компилятора **-define** действует так же, как директива препроцессора [#define](../preprocessor-directives/preprocessor-define.md), однако, в отличие от нее, применяется ко всем файлам проекта.</span><span class="sxs-lookup"><span data-stu-id="71862-109">The **-define** option has the same effect as using a [#define](../preprocessor-directives/preprocessor-define.md) preprocessor directive except that the compiler option is in effect for all files in the project.</span></span> <span data-ttu-id="71862-110">Символ остается определенным в файле исходного кода до тех пор, пока определение не будет отменено с помощью директивы [#undef](../preprocessor-directives/preprocessor-undef.md) в файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="71862-110">A symbol remains defined in a source file until an [#undef](../preprocessor-directives/preprocessor-undef.md) directive in the source file removes the definition.</span></span> <span data-ttu-id="71862-111">При использовании параметра -define директива `#undef` в одном файле не действует для других файлов исходного кода в проекте.</span><span class="sxs-lookup"><span data-stu-id="71862-111">When you use the -define option, an `#undef` directive in one file has no effect on other source code files in the project.</span></span>  
  
 <span data-ttu-id="71862-112">Вы можете использовать символы, созданные этим параметром, с директивами [#if](../preprocessor-directives/preprocessor-if.md), [#else](../preprocessor-directives/preprocessor-else.md), [#elif](../preprocessor-directives/preprocessor-elif.md) и [#endif](../preprocessor-directives/preprocessor-endif.md) для условной компиляции исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="71862-112">You can use symbols created by this option with [#if](../preprocessor-directives/preprocessor-if.md), [#else](../preprocessor-directives/preprocessor-else.md), [#elif](../preprocessor-directives/preprocessor-elif.md), and [#endif](../preprocessor-directives/preprocessor-endif.md) to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="71862-113">**-d** является краткой формой **-define**.</span><span class="sxs-lookup"><span data-stu-id="71862-113">**-d** is the short form of **-define**.</span></span>  
  
 <span data-ttu-id="71862-114">Вы можете определить несколько символов с помощью **-define**, разделяя их имена точкой с запятой или запятой.</span><span class="sxs-lookup"><span data-stu-id="71862-114">You can define multiple symbols with **-define** by using a semicolon or comma to separate symbol names.</span></span> <span data-ttu-id="71862-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="71862-115">For example:</span></span>  
  
```console  
-define:DEBUG;TUESDAY  
```  
  
 <span data-ttu-id="71862-116">Компилятор C# сам по себе не определяет символы и макросы, которые можно использовать в исходном коде. Все такие определения задаются пользователем.</span><span class="sxs-lookup"><span data-stu-id="71862-116">The C# compiler itself defines no symbols or macros that you can use in your source code; all symbol definitions must be user-defined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71862-117">C# `#define` не поддерживает присваивание значения символу, как, например, в языке C++.</span><span class="sxs-lookup"><span data-stu-id="71862-117">The C# `#define` does not allow a symbol to be given a value, as in languages such as C++.</span></span> <span data-ttu-id="71862-118">Например, с помощью директивы `#define` нельзя создать макрос или определить константу.</span><span class="sxs-lookup"><span data-stu-id="71862-118">For example, `#define` cannot be used to create a macro or to define a constant.</span></span> <span data-ttu-id="71862-119">Чтобы определить константу, используйте переменную `enum`.</span><span class="sxs-lookup"><span data-stu-id="71862-119">If you need to define a constant, use an `enum` variable.</span></span> <span data-ttu-id="71862-120">Для создания макросов в стиле C++ необходимо использовать альтернативные способы, например универсальные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="71862-120">If you want to create a C++ style macro, consider alternatives such as generics.</span></span> <span data-ttu-id="71862-121">Поскольку макросы по своей природе подвержены ошибкам, в C# они запрещены, однако вместо них предлагаются более безопасные альтернативы.</span><span class="sxs-lookup"><span data-stu-id="71862-121">Since macros are notoriously error-prone, C# disallows their use but provides safer alternatives.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="71862-122">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="71862-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="71862-123">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="71862-123">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="71862-124">На вкладке **Сборка** введите символ, который требуется определить, в поле **Символы условной компиляции**.</span><span class="sxs-lookup"><span data-stu-id="71862-124">On the **Build** tab, type the symbol that is to be defined in the **Conditional compilation symbols** box.</span></span> <span data-ttu-id="71862-125">Например, для представленного ниже примера кода просто введите `xx` в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="71862-125">For example, if you are using the code example that follows, just type `xx` into the text box.</span></span>  
  
 <span data-ttu-id="71862-126">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span><span class="sxs-lookup"><span data-stu-id="71862-126">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71862-127">Пример</span><span class="sxs-lookup"><span data-stu-id="71862-127">Example</span></span>  
  
```csharp  
// preprocessor_define.cs  
// compile with: -define:xx  
// or uncomment the next line  
// #define xx  
using System;  
public class Test
{  
    public static void Main()
    {  
        #if (xx)
            Console.WriteLine("xx defined");  
        #else  
            Console.WriteLine("xx not defined");  
        #endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="71862-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="71862-128">See also</span></span>

- [<span data-ttu-id="71862-129">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="71862-129">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="71862-130">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="71862-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
