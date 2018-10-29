---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: 2c7fb6c88477899a0cf08a467e8f23d687b90c90
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50201903"
---
# <a name="-rootnamespace"></a><span data-ttu-id="6ab45-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="6ab45-102">-rootnamespace</span></span>
<span data-ttu-id="6ab45-103">Задает пространство имен для всех объявлений типов.</span><span class="sxs-lookup"><span data-stu-id="6ab45-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ab45-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ab45-104">Syntax</span></span>  
  
```  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="6ab45-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6ab45-105">Arguments</span></span>  
  
|<span data-ttu-id="6ab45-106">Термин</span><span class="sxs-lookup"><span data-stu-id="6ab45-106">Term</span></span>|<span data-ttu-id="6ab45-107">Определение</span><span class="sxs-lookup"><span data-stu-id="6ab45-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="6ab45-108">Имя пространства имен, в котором находятся все объявления типов для текущего проекта.</span><span class="sxs-lookup"><span data-stu-id="6ab45-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ab45-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6ab45-109">Remarks</span></span>  
 <span data-ttu-id="6ab45-110">При использовании исполняемого файла Visual Studio (Devenv.exe) для компиляции в проект, созданный в среде разработки Visual Studio, используйте `-rootnamespace` для указания значения <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="6ab45-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="6ab45-111">См. в разделе [командной строки devenv](/visualstudio/ide/reference/devenv-command-line-switches) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="6ab45-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="6ab45-112">Используйте среду дизассемблера MSIL (`Ildasm.exe`) для просмотра имен пространств имен в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="6ab45-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="6ab45-113">Чтобы задать - rootnamespace в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6ab45-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="6ab45-114">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="6ab45-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6ab45-115">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6ab45-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="6ab45-116">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="6ab45-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="6ab45-117">3.  Измените значение в **корневое пространство имен** поле.</span><span class="sxs-lookup"><span data-stu-id="6ab45-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6ab45-118">Пример</span><span class="sxs-lookup"><span data-stu-id="6ab45-118">Example</span></span>  
 <span data-ttu-id="6ab45-119">Следующий код компилирует `In.vb` и помещает все объявления типов в пространстве имен `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="6ab45-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ab45-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6ab45-120">See also</span></span>

- [<span data-ttu-id="6ab45-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="6ab45-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
- [<span data-ttu-id="6ab45-122">Ildasm.exe (дизассемблер IL)</span><span class="sxs-lookup"><span data-stu-id="6ab45-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)  
- [<span data-ttu-id="6ab45-123">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="6ab45-123">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
