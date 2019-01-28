---
title: -main (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 36e5f10a61711e3245fa4b69dc583f4bb78e55e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558592"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="7dd6a-102">-main (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="7dd6a-102">-main (C# Compiler Options)</span></span>
<span data-ttu-id="7dd6a-103">Этот параметр определяет класс, который содержит точку входа в программу, если метод **Main** содержит сразу несколько классов.</span><span class="sxs-lookup"><span data-stu-id="7dd6a-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dd6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7dd6a-104">Syntax</span></span>  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="7dd6a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7dd6a-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="7dd6a-106">Тип, содержащий метод **Main**.</span><span class="sxs-lookup"><span data-stu-id="7dd6a-106">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="7dd6a-107">Указанное имя класса должно быть полным; оно должно включать полное пространство имен, содержащее ключевое слово class, за которым следует имя класса.</span><span class="sxs-lookup"><span data-stu-id="7dd6a-107">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="7dd6a-108">Например, если метод `Main` находится в классе `Program` в пространстве имен `MyApplication.Core`, необходимо указать параметр компилятора `-main:MyApplication.Core.Program`.</span><span class="sxs-lookup"><span data-stu-id="7dd6a-108">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7dd6a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7dd6a-109">Remarks</span></span>  
 <span data-ttu-id="7dd6a-110">Если в компиляцию входят несколько типов с методом [Main](../../../csharp/programming-guide/main-and-command-args/index.md), можно указать, какой из них содержит метод **Main**, который нужно использовать как точку входа в программу.</span><span class="sxs-lookup"><span data-stu-id="7dd6a-110">If your compilation includes more than one type with a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="7dd6a-111">Этот параметр предназначен для использования при компиляции файлов EXE.</span><span class="sxs-lookup"><span data-stu-id="7dd6a-111">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="7dd6a-112">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7dd6a-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="7dd6a-113">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="7dd6a-113">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="7dd6a-114">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="7dd6a-114">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="7dd6a-115">Измените свойство **Автоматически запускаемый объект**.</span><span class="sxs-lookup"><span data-stu-id="7dd6a-115">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="7dd6a-116">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="7dd6a-116">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dd6a-117">Пример</span><span class="sxs-lookup"><span data-stu-id="7dd6a-117">Example</span></span>  
 <span data-ttu-id="7dd6a-118">Скомпилируйте `t2.cs` и `t3.cs`, указав, что метод **Main** будет находиться в `Test2`:</span><span class="sxs-lookup"><span data-stu-id="7dd6a-118">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="7dd6a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7dd6a-119">See also</span></span>

- [<span data-ttu-id="7dd6a-120">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="7dd6a-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="7dd6a-121">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="7dd6a-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
