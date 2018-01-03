---
title: /out (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53b77dec53be1d97c5f2526cb117933a2b8fe046
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="out-visual-basic"></a><span data-ttu-id="31cd1-102">/out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31cd1-102">/out (Visual Basic)</span></span>
<span data-ttu-id="31cd1-103">Задает имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="31cd1-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31cd1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31cd1-104">Syntax</span></span>  
  
```  
/out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="31cd1-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="31cd1-105">Arguments</span></span>  
  
|<span data-ttu-id="31cd1-106">Термин</span><span class="sxs-lookup"><span data-stu-id="31cd1-106">Term</span></span>|<span data-ttu-id="31cd1-107">Определение</span><span class="sxs-lookup"><span data-stu-id="31cd1-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="31cd1-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="31cd1-108">Required.</span></span> <span data-ttu-id="31cd1-109">Создает имя файла выходных данных компилятора.</span><span class="sxs-lookup"><span data-stu-id="31cd1-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="31cd1-110">Если имя файла содержит пробелы, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="31cd1-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31cd1-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="31cd1-111">Remarks</span></span>  
 <span data-ttu-id="31cd1-112">Укажите полное имя и расширение файла для создания.</span><span class="sxs-lookup"><span data-stu-id="31cd1-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="31cd1-113">Если этого не сделать, файл .exe планка файл исходного кода, содержащий `Sub Main` процедуры и DLL-файла будет использовано имя первого файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="31cd1-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="31cd1-114">Если указать имя файла без расширения .exe или .dll, компилятор автоматически добавляет расширение, в зависимости от значения, указанные для `/target` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="31cd1-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `/target` compiler option.</span></span>  
  
|<span data-ttu-id="31cd1-115">Чтобы установить параметр/out в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="31cd1-115">To set /out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="31cd1-116">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="31cd1-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="31cd1-117">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="31cd1-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="31cd1-118">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="31cd1-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="31cd1-119">3.  Измените значение в **имя сборки** поле.</span><span class="sxs-lookup"><span data-stu-id="31cd1-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="31cd1-120">Пример</span><span class="sxs-lookup"><span data-stu-id="31cd1-120">Example</span></span>  
 <span data-ttu-id="31cd1-121">Следующий код компилирует `T2.vb` и создает выходной файл `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="31cd1-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="31cd1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="31cd1-122">See Also</span></span>  
 [<span data-ttu-id="31cd1-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="31cd1-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="31cd1-124">/ Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31cd1-124">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="31cd1-125">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="31cd1-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
