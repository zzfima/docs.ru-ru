---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 5dcf9dc5cc0987e965aba7fd2b8821252e19a655
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788899"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="81f9d-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81f9d-102">-out (Visual Basic)</span></span>
<span data-ttu-id="81f9d-103">Задает имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="81f9d-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81f9d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81f9d-104">Syntax</span></span>  
  
```  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="81f9d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="81f9d-105">Arguments</span></span>  
  
|<span data-ttu-id="81f9d-106">Термин</span><span class="sxs-lookup"><span data-stu-id="81f9d-106">Term</span></span>|<span data-ttu-id="81f9d-107">Определение</span><span class="sxs-lookup"><span data-stu-id="81f9d-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="81f9d-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="81f9d-108">Required.</span></span> <span data-ttu-id="81f9d-109">Создает имя выходного файла компилятора.</span><span class="sxs-lookup"><span data-stu-id="81f9d-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="81f9d-110">Если имя файла содержит пробел, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="81f9d-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81f9d-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="81f9d-111">Remarks</span></span>  
 <span data-ttu-id="81f9d-112">Укажите полное имя и расширение файла для создания.</span><span class="sxs-lookup"><span data-stu-id="81f9d-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="81f9d-113">Если этого не сделать, файл .exe принимает его имя из исходного кода файла, содержащего `Sub Main` процедуры и DLL-файла — имя первого файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="81f9d-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="81f9d-114">Если указать имя файла без расширения .exe или .dll, компилятор автоматически добавляет расширение, в зависимости от значения, указанные для `-target` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="81f9d-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="81f9d-115">Чтобы задать - out в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="81f9d-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="81f9d-116">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="81f9d-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="81f9d-117">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="81f9d-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="81f9d-118">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="81f9d-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="81f9d-119">3.  Измените значение в **имя сборки** поле.</span><span class="sxs-lookup"><span data-stu-id="81f9d-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="81f9d-120">Пример</span><span class="sxs-lookup"><span data-stu-id="81f9d-120">Example</span></span>  
 <span data-ttu-id="81f9d-121">Следующий код компилирует `T2.vb` и создает выходной файл `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="81f9d-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="81f9d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="81f9d-122">See also</span></span>

- [<span data-ttu-id="81f9d-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="81f9d-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="81f9d-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81f9d-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="81f9d-125">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="81f9d-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
