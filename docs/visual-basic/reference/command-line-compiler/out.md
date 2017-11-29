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
ms.openlocfilehash: d98a9f3cadc42021c302915cfc5b058b41e11ec6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="out-visual-basic"></a><span data-ttu-id="ac8e9-102">/out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac8e9-102">/out (Visual Basic)</span></span>
<span data-ttu-id="ac8e9-103">Задает имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="ac8e9-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac8e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac8e9-104">Syntax</span></span>  
  
```  
/out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac8e9-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ac8e9-105">Arguments</span></span>  
  
|<span data-ttu-id="ac8e9-106">Термин</span><span class="sxs-lookup"><span data-stu-id="ac8e9-106">Term</span></span>|<span data-ttu-id="ac8e9-107">Определение</span><span class="sxs-lookup"><span data-stu-id="ac8e9-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="ac8e9-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ac8e9-108">Required.</span></span> <span data-ttu-id="ac8e9-109">Создает имя файла выходных данных компилятора.</span><span class="sxs-lookup"><span data-stu-id="ac8e9-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="ac8e9-110">Если имя файла содержит пробелы, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="ac8e9-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac8e9-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac8e9-111">Remarks</span></span>  
 <span data-ttu-id="ac8e9-112">Укажите полное имя и расширение файла для создания.</span><span class="sxs-lookup"><span data-stu-id="ac8e9-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="ac8e9-113">Если этого не сделать, файл .exe планка файл исходного кода, содержащий `Sub Main` процедуры и DLL-файла будет использовано имя первого файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="ac8e9-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="ac8e9-114">Если указать имя файла без расширения .exe или .dll, компилятор автоматически добавляет расширение, в зависимости от значения, указанные для `/target` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="ac8e9-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `/target` compiler option.</span></span>  
  
|<span data-ttu-id="ac8e9-115">Чтобы установить параметр/out в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ac8e9-115">To set /out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="ac8e9-116">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="ac8e9-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ac8e9-117">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ac8e9-117">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="ac8e9-118">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="ac8e9-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="ac8e9-119">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="ac8e9-119">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="ac8e9-120">3.  Измените значение в **имя сборки** поле.</span><span class="sxs-lookup"><span data-stu-id="ac8e9-120">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ac8e9-121">Пример</span><span class="sxs-lookup"><span data-stu-id="ac8e9-121">Example</span></span>  
 <span data-ttu-id="ac8e9-122">Следующий код компилирует `T2.vb` и создает выходной файл `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="ac8e9-122">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac8e9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ac8e9-123">See Also</span></span>  
 [<span data-ttu-id="ac8e9-124">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="ac8e9-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="ac8e9-125">/ Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac8e9-125">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="ac8e9-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="ac8e9-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
