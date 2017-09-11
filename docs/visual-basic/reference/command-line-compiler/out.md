---
title: "/ out (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 489a9015718a581c793cd1217ba073625929daf3
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="out-visual-basic"></a><span data-ttu-id="10035-102">/out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10035-102">/out (Visual Basic)</span></span>
<span data-ttu-id="10035-103">Задает имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="10035-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10035-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10035-104">Syntax</span></span>  
  
```  
/out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="10035-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="10035-105">Arguments</span></span>  
  
|<span data-ttu-id="10035-106">Термин</span><span class="sxs-lookup"><span data-stu-id="10035-106">Term</span></span>|<span data-ttu-id="10035-107">Определение</span><span class="sxs-lookup"><span data-stu-id="10035-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="10035-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="10035-108">Required.</span></span> <span data-ttu-id="10035-109">Имя выходного файла, компилятор создает.</span><span class="sxs-lookup"><span data-stu-id="10035-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="10035-110">Если имя файла содержит пробел, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="10035-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10035-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="10035-111">Remarks</span></span>  
 <span data-ttu-id="10035-112">Укажите полное имя и расширение файла для создания.</span><span class="sxs-lookup"><span data-stu-id="10035-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="10035-113">Если этого не сделать, файл .exe принимает его имя файла исходного кода, содержащего `Sub Main` процедуры и DLL-файла — имя первого файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="10035-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="10035-114">Если указать имя файла без расширения .exe или .dll, компилятор автоматически добавляет расширение, в зависимости от значения, указанного для `/target` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="10035-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `/target` compiler option.</span></span>  
  
|<span data-ttu-id="10035-115">Чтобы установить параметр/out в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="10035-115">To set /out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="10035-116">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="10035-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="10035-117">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="10035-117">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="10035-118">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="10035-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="10035-119">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="10035-119">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="10035-120">3.  Измените значение в **имя сборки** поле.</span><span class="sxs-lookup"><span data-stu-id="10035-120">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="10035-121">Пример</span><span class="sxs-lookup"><span data-stu-id="10035-121">Example</span></span>  
 <span data-ttu-id="10035-122">Следующий код компилирует `T2.vb` и создает выходной файл `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="10035-122">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="10035-123">См. также</span><span class="sxs-lookup"><span data-stu-id="10035-123">See Also</span></span>  
 <span data-ttu-id="10035-124">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="10035-124">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="10035-125"> [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="10035-125"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="10035-126"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="10035-126"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
