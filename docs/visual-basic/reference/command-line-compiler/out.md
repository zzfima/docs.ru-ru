---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 6b005ac26e3fffad350cb4ce52f7757c9fff2ac1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005329"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="c1109-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1109-102">-out (Visual Basic)</span></span>
<span data-ttu-id="c1109-103">Задает имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="c1109-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1109-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1109-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="c1109-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c1109-105">Arguments</span></span>  
  
|<span data-ttu-id="c1109-106">Термин</span><span class="sxs-lookup"><span data-stu-id="c1109-106">Term</span></span>|<span data-ttu-id="c1109-107">Определение</span><span class="sxs-lookup"><span data-stu-id="c1109-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="c1109-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c1109-108">Required.</span></span> <span data-ttu-id="c1109-109">Имя выходного файла, создаваемого компилятором.</span><span class="sxs-lookup"><span data-stu-id="c1109-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="c1109-110">Если имя файла содержит пробел, заключите его в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="c1109-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1109-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c1109-111">Remarks</span></span>  
 <span data-ttu-id="c1109-112">Укажите полное имя и расширение создаваемого файла.</span><span class="sxs-lookup"><span data-stu-id="c1109-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="c1109-113">Если этого не сделать, exe-файл принимает имя из файла исходного кода, содержащего процедуру `Sub Main`, а имя файла. dll — из первого файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="c1109-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="c1109-114">Если указать имя файла без расширения EXE или DLL, компилятор автоматически добавит расширение в зависимости от значения, указанного для параметра компилятора `-target`.</span><span class="sxs-lookup"><span data-stu-id="c1109-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="c1109-115">Установка в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c1109-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c1109-116">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="c1109-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c1109-117">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c1109-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c1109-118">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="c1109-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="c1109-119">3.  Измените значение в поле **имя сборки** .</span><span class="sxs-lookup"><span data-stu-id="c1109-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c1109-120">Пример</span><span class="sxs-lookup"><span data-stu-id="c1109-120">Example</span></span>  
 <span data-ttu-id="c1109-121">Следующий код компилирует `T2.vb` и создает выходной файл `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="c1109-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1109-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c1109-122">See also</span></span>

- [<span data-ttu-id="c1109-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="c1109-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c1109-124">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1109-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="c1109-125">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="c1109-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
