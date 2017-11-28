---
title: "-main (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4a6dca6e62dbf69783babf2e16dc4e7c36c6705c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="main-c-compiler-options"></a><span data-ttu-id="bc90b-102">/main (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="bc90b-102">/main (C# Compiler Options)</span></span>
<span data-ttu-id="bc90b-103">Этот параметр определяет класс, который содержит точку входа в программу, если метод **Main** содержит сразу несколько классов.</span><span class="sxs-lookup"><span data-stu-id="bc90b-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc90b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc90b-104">Syntax</span></span>  
  
```console  
/main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="bc90b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bc90b-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="bc90b-106">Тип, содержащий метод **Main**.</span><span class="sxs-lookup"><span data-stu-id="bc90b-106">The type that contains the **Main** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc90b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc90b-107">Remarks</span></span>  
 <span data-ttu-id="bc90b-108">Если в компиляцию входят несколько типов с методом [Main](../../../csharp/programming-guide/main-and-command-args/index.md), можно указать, какой из них содержит метод **Main**, который нужно использовать как точку входа в программу.</span><span class="sxs-lookup"><span data-stu-id="bc90b-108">If your compilation includes more than one type with a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="bc90b-109">Этот параметр предназначен для использования при компиляции файлов EXE.</span><span class="sxs-lookup"><span data-stu-id="bc90b-109">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="bc90b-110">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bc90b-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="bc90b-111">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="bc90b-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="bc90b-112">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="bc90b-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="bc90b-113">Измените свойство **Автоматически запускаемый объект**.</span><span class="sxs-lookup"><span data-stu-id="bc90b-113">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="bc90b-114">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc90b-114">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc90b-115">Пример</span><span class="sxs-lookup"><span data-stu-id="bc90b-115">Example</span></span>  
 <span data-ttu-id="bc90b-116">Скомпилируйте `t2.cs` и `t3.cs`, указав, что метод **Main** будет находиться в `Test2`:</span><span class="sxs-lookup"><span data-stu-id="bc90b-116">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc90b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bc90b-117">See Also</span></span>  
 [<span data-ttu-id="bc90b-118">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="bc90b-118">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="bc90b-119">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="bc90b-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
