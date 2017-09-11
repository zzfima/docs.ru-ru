---
title: "-main (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /main
dev_langs:
- CSharp
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: 14
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
ms.openlocfilehash: eee7ef4698f4b6bf7c90ff8e22a1a3ae106bec35
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="main-c-compiler-options"></a><span data-ttu-id="40800-102">/main (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="40800-102">/main (C# Compiler Options)</span></span>
<span data-ttu-id="40800-103">Этот параметр определяет класс, который содержит точку входа в программу, если метод **Main** содержит сразу несколько классов.</span><span class="sxs-lookup"><span data-stu-id="40800-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40800-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40800-104">Syntax</span></span>  
  
```console  
/main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="40800-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="40800-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="40800-106">Тип, содержащий метод **Main**.</span><span class="sxs-lookup"><span data-stu-id="40800-106">The type that contains the **Main** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40800-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="40800-107">Remarks</span></span>  
 <span data-ttu-id="40800-108">Если в компиляцию входят несколько типов с методом [Main](../../../csharp/programming-guide/main-and-command-args/index.md), можно указать, какой из них содержит метод **Main**, который нужно использовать как точку входа в программу.</span><span class="sxs-lookup"><span data-stu-id="40800-108">If your compilation includes more than one type with a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="40800-109">Этот параметр предназначен для использования при компиляции файлов EXE.</span><span class="sxs-lookup"><span data-stu-id="40800-109">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="40800-110">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="40800-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="40800-111">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="40800-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="40800-112">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="40800-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="40800-113">Измените свойство **Автоматически запускаемый объект**.</span><span class="sxs-lookup"><span data-stu-id="40800-113">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="40800-114">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="40800-114">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40800-115">Пример</span><span class="sxs-lookup"><span data-stu-id="40800-115">Example</span></span>  
 <span data-ttu-id="40800-116">Скомпилируйте `t2.cs` и `t3.cs`, указав, что метод **Main** будет находиться в `Test2`:</span><span class="sxs-lookup"><span data-stu-id="40800-116">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="40800-117">См. также</span><span class="sxs-lookup"><span data-stu-id="40800-117">See Also</span></span>  
 <span data-ttu-id="40800-118">[Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="40800-118">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="40800-119">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="40800-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

