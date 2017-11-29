---
title: "-checked (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e02f82bb0dd2952bd2f192af7ff233194a045619
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="checked-c-compiler-options"></a><span data-ttu-id="5723e-102">/checked (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="5723e-102">/checked (C# Compiler Options)</span></span>
<span data-ttu-id="5723e-103">Параметр **/checked** указывает, будет ли находящийся вне области действия ключевых слов [checked](../../../csharp/language-reference/keywords/checked.md) или [unchecked](../../../csharp/language-reference/keywords/unchecked.md) целочисленный арифметический оператор, в результате выполнения которого получено значение, выходящее за установленный для данного типа данных диапазон значений, приводить к возникновению исключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5723e-103">The **/checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../../../csharp/language-reference/keywords/checked.md) or [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5723e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5723e-104">Syntax</span></span>  
  
```console  
/checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="5723e-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="5723e-105">Remarks</span></span>  
 <span data-ttu-id="5723e-106">Действие параметра **/checked** не затрагивает целочисленный арифметический оператор, находящийся вне области действия ключевых слов `checked` или `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="5723e-106">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **/checked** option.</span></span>  
  
 <span data-ttu-id="5723e-107">Если в результате выполнения целочисленного арифметического оператора, находящегося вне области действия ключевых слов `checked` или `unchecked`, получено значение, выходящее за установленный для данного типа данных диапазон значений, и в компиляции использовался **/checked+** (**/checked**), то этот оператор будет приводить к возникновению исключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5723e-107">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **/checked+** (**/checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="5723e-108">Если в компиляции использовался **/checked-**, оператор не будет приводить к исключению во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5723e-108">If **/checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="5723e-109">**/checked-** является значением по умолчанию для данного параметра.</span><span class="sxs-lookup"><span data-stu-id="5723e-109">The default value for this option is **/checked-**.</span></span> <span data-ttu-id="5723e-110">Одним из сценариев использования **/checked-** является создание крупных приложений.</span><span class="sxs-lookup"><span data-stu-id="5723e-110">One scenario for using **/checked-** is in building large applications.</span></span> <span data-ttu-id="5723e-111">Иногда автоматизированные средства используются для построения подобных приложений, и в данной ситуации они могут автоматически задать + для **/checked**.</span><span class="sxs-lookup"><span data-stu-id="5723e-111">Sometimes automated tools are used to build such applications, and such a tool might automatically set **/checked** to +.</span></span> <span data-ttu-id="5723e-112">Чтобы переопределить глобальное значение по умолчанию, задайте**/checked-**.</span><span class="sxs-lookup"><span data-stu-id="5723e-112">You can override the tool's global default by specifying **/checked-**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5723e-113">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5723e-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="5723e-114">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="5723e-114">Open the project's **Properties** page.</span></span> <span data-ttu-id="5723e-115">Дополнительные сведения см. в разделе [Страница "Сборка" в конструкторе проектов (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="5723e-115">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="5723e-116">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="5723e-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="5723e-117">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="5723e-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="5723e-118">Измените свойство **Проверять арифметические переполнения и потери точности**.</span><span class="sxs-lookup"><span data-stu-id="5723e-118">Modify the **Check for arithmetic overflow/underflow** property.</span></span>  
  
 <span data-ttu-id="5723e-119">Программный доступ к этому параметру компилятора описан в статье <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span><span class="sxs-lookup"><span data-stu-id="5723e-119">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5723e-120">Пример</span><span class="sxs-lookup"><span data-stu-id="5723e-120">Example</span></span>  
 <span data-ttu-id="5723e-121">Следующая команда используется для компиляции `t2.cs`.</span><span class="sxs-lookup"><span data-stu-id="5723e-121">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="5723e-122">Использование `/checked` в команде указывает, что целочисленный арифметический оператор, находящийся вне области действия ключевых слов `checked` или `unchecked`, и значение результата его выполнения, выходящее за установленный для данного типа данных диапазон значений, будут приводить к возникновению исключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5723e-122">The use of `/checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs /checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="5723e-123">См. также</span><span class="sxs-lookup"><span data-stu-id="5723e-123">See Also</span></span>  
 [<span data-ttu-id="5723e-124">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="5723e-124">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="5723e-125">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="5723e-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
