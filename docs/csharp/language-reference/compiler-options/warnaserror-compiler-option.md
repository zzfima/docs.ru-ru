---
title: -warnaserror (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /warnaserror
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
ms.openlocfilehash: 7d43941629e933ac5a9e9c9d6a1388b6194f8d99
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503475"
---
# <a name="-warnaserror-c-compiler-options"></a><span data-ttu-id="609d0-102">-warnaserror (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="609d0-102">-warnaserror (C# Compiler Options)</span></span>
<span data-ttu-id="609d0-103">Параметр **-warnaserror+** предписывает обрабатывать все предупреждения как ошибки</span><span class="sxs-lookup"><span data-stu-id="609d0-103">The **-warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="609d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="609d0-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="609d0-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="609d0-105">Remarks</span></span>  
 <span data-ttu-id="609d0-106">Все сообщения, которые до этого получали статус предупреждений, будут возвращаться как ошибки, в результате чего процесс построения прерывается без создания выходных файлов.</span><span class="sxs-lookup"><span data-stu-id="609d0-106">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="609d0-107">По умолчанию действует параметр **-warnaserror-** , при котором наличие предупреждений не препятствует созданию выходного файла.</span><span class="sxs-lookup"><span data-stu-id="609d0-107">By default, **-warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="609d0-108">Если задан параметр **-warnaserror** или эквивалентный ему **-warnaserror+** , все предупреждения обрабатываются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="609d0-108">**-warnaserror**, which is the same as **-warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="609d0-109">Если требуется обрабатывать как ошибки только конкретные предупреждения, укажите их номера через запятую.</span><span class="sxs-lookup"><span data-stu-id="609d0-109">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span> <span data-ttu-id="609d0-110">Набор всех предупреждений о допустимости значений NULL можно указать с помощью сокращения **nullable**.</span><span class="sxs-lookup"><span data-stu-id="609d0-110">The set of all nullability warnings can be specified with the **nullable** shorthand.</span></span>
  
 <span data-ttu-id="609d0-111">Параметр [-warn](./warn-compiler-option.md) позволяет указать уровень предупреждений, которые будет отображать компилятор.</span><span class="sxs-lookup"><span data-stu-id="609d0-111">Use [-warn](./warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="609d0-112">Параметр [-nowarn](./nowarn-compiler-option.md) позволяет отключать определенные предупреждения.</span><span class="sxs-lookup"><span data-stu-id="609d0-112">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="609d0-113">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="609d0-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="609d0-114">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="609d0-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="609d0-115">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="609d0-115">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="609d0-116">Измените свойство **Обрабатывать предупреждения как ошибки**.</span><span class="sxs-lookup"><span data-stu-id="609d0-116">Modify the **Treat Warnings As Errors** property.</span></span>  
  
 <span data-ttu-id="609d0-117">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span><span class="sxs-lookup"><span data-stu-id="609d0-117">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="609d0-118">Пример</span><span class="sxs-lookup"><span data-stu-id="609d0-118">Example</span></span>  
 <span data-ttu-id="609d0-119">Компиляция файла `in.cs` без отображения предупреждений:</span><span class="sxs-lookup"><span data-stu-id="609d0-119">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652,nullable in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="609d0-120">См. также</span><span class="sxs-lookup"><span data-stu-id="609d0-120">See also</span></span>

- [<span data-ttu-id="609d0-121">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="609d0-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="609d0-122">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="609d0-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
