---
title: "-warnaserror (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /warnaserror
dev_langs:
- CSharp
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
caps.latest.revision: 15
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
ms.openlocfilehash: df29fd760e0e4a002f1b5078d85370a74f322e23
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="warnaserror-c-compiler-options"></a><span data-ttu-id="3d332-102">/warnaserror (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="3d332-102">/warnaserror (C# Compiler Options)</span></span>
<span data-ttu-id="3d332-103">Параметр **/warnaserror+** указывает обрабатывать все предупреждения как ошибки</span><span class="sxs-lookup"><span data-stu-id="3d332-103">The **/warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d332-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d332-104">Syntax</span></span>  
  
```console  
/warnaserror[<U>+</U> | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="3d332-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d332-105">Remarks</span></span>  
 <span data-ttu-id="3d332-106">Все сообщения, которые до этого получали статус предупреждений, будут возвращаться как ошибки, в результате чего процесс построения прерывается без создания выходных файлов.</span><span class="sxs-lookup"><span data-stu-id="3d332-106">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="3d332-107">По умолчанию действует параметр **/warnaserror-**, при котором наличие предупреждений не препятствует созданию выходных файлов.</span><span class="sxs-lookup"><span data-stu-id="3d332-107">By default, **/warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="3d332-108">Если задан параметр **/warnaserror** или эквивалентный ему **/warnaserror+**, все предупреждения обрабатываются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="3d332-108">**/warnaserror**, which is the same as **/warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="3d332-109">Если требуется обрабатывать как ошибки только конкретные предупреждения, укажите их номера через запятую.</span><span class="sxs-lookup"><span data-stu-id="3d332-109">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
 <span data-ttu-id="3d332-110">Параметр [/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md) позволяет указать уровень предупреждений, которые будет отображать компилятор.</span><span class="sxs-lookup"><span data-stu-id="3d332-110">Use [/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="3d332-111">Параметр [/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) позволяет отключать определенные предупреждения.</span><span class="sxs-lookup"><span data-stu-id="3d332-111">Use [/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="3d332-112">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3d332-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="3d332-113">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="3d332-113">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="3d332-114">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="3d332-114">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="3d332-115">Измените свойство **Обрабатывать предупреждения как ошибки**.</span><span class="sxs-lookup"><span data-stu-id="3d332-115">Modify the **Treat Warnings As Errors** property.</span></span>  
  
     <span data-ttu-id="3d332-116">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="3d332-116">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d332-117">Пример</span><span class="sxs-lookup"><span data-stu-id="3d332-117">Example</span></span>  
 <span data-ttu-id="3d332-118">Компиляция файла `in.cs` без отображения предупреждений:</span><span class="sxs-lookup"><span data-stu-id="3d332-118">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc /warnaserror in.cs  
csc /warnaserror:642,649,652 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d332-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3d332-119">See Also</span></span>  
 <span data-ttu-id="3d332-120">[Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="3d332-120">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="3d332-121">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="3d332-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

