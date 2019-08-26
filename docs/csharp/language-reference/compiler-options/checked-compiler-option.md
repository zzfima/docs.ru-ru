---
title: -checked (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: 4e07698e7abdad00983b61412fa2a57e651d4d46
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606997"
---
# <a name="-checked-c-compiler-options"></a><span data-ttu-id="7d040-102">-checked (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="7d040-102">-checked (C# Compiler Options)</span></span>
<span data-ttu-id="7d040-103">Параметр **-checked** указывает, будет ли находящийся вне области действия ключевых слов [checked](../keywords/checked.md) или [unchecked](../keywords/unchecked.md) целочисленный арифметический оператор, в результате выполнения которого получено значение, выходящее за установленный для данного типа данных диапазон значений, приводить к возникновению исключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7d040-103">The **-checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../keywords/checked.md) or [unchecked](../keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d040-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d040-104">Syntax</span></span>  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="7d040-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d040-105">Remarks</span></span>  
 <span data-ttu-id="7d040-106">Действие параметра **-checked** не затрагивает целочисленный арифметический оператор, находящийся вне области действия ключевых слов `checked` или `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="7d040-106">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **-checked** option.</span></span>  
  
 <span data-ttu-id="7d040-107">Если в результате выполнения целочисленного арифметического оператора, находящегося вне области действия ключевых слов `checked` или `unchecked`, получено значение, выходящее за установленный для данного типа данных диапазон значений, и в компиляции использовался параметр **-checked+** (или **-checked**), то во время выполнения возникнет исключение из-за этого оператора.</span><span class="sxs-lookup"><span data-stu-id="7d040-107">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **-checked+** (or **-checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="7d040-108">Если в компиляции использовался параметр **-checked-** , оператор не будет приводить к исключению во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7d040-108">If **-checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="7d040-109">Значение этого параметра по умолчанию — **-checked-** ; проверка переполнения отключена.</span><span class="sxs-lookup"><span data-stu-id="7d040-109">The default value for this option is **-checked-**; overflow checking is disabled.</span></span>
 
 <span data-ttu-id="7d040-110">В некоторых случаях автоматизированные утилиты, которые используются для сборки крупных приложений, устанавливают значение "+" для параметра "-checked".</span><span class="sxs-lookup"><span data-stu-id="7d040-110">Sometimes, automated tools that are used to build large applications set -checked to +.</span></span> <span data-ttu-id="7d040-111">Один из сценариев для использования "-checked-" — переопределить глобальное значение по умолчанию, указав "-checked-".</span><span class="sxs-lookup"><span data-stu-id="7d040-111">One scenario for using -checked- is to override the tool's global default by specifying -checked-.</span></span>
 
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="7d040-112">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d040-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="7d040-113">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="7d040-113">Open the project's **Properties** page.</span></span> <span data-ttu-id="7d040-114">Дополнительные сведения см. в разделе [Страница "Сборка" в конструкторе проектов (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="7d040-114">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="7d040-115">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="7d040-115">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="7d040-116">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="7d040-116">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="7d040-117">Измените свойство **Проверять арифметические переполнения и потери точности**.</span><span class="sxs-lookup"><span data-stu-id="7d040-117">Modify the **Check for arithmetic overflow/underflow** property.</span></span>  
  
 <span data-ttu-id="7d040-118">Программный доступ к этому параметру компилятора описан в статье <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d040-118">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d040-119">Пример</span><span class="sxs-lookup"><span data-stu-id="7d040-119">Example</span></span>  
 <span data-ttu-id="7d040-120">Следующая команда используется для компиляции `t2.cs`.</span><span class="sxs-lookup"><span data-stu-id="7d040-120">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="7d040-121">Использование `-checked` в команде указывает, что целочисленный арифметический оператор, находящийся вне области действия ключевых слов `checked` или `unchecked`, и значение результата его выполнения, выходящее за установленный для данного типа данных диапазон значений, будут приводить к возникновению исключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7d040-121">The use of `-checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d040-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7d040-122">See also</span></span>

- [<span data-ttu-id="7d040-123">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="7d040-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="7d040-124">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="7d040-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
