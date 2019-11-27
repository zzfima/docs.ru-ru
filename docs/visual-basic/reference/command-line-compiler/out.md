---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 67366e13e4dceea4772d0730222413cb25b4e8b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352385"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="9b9e8-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b9e8-102">-out (Visual Basic)</span></span>
<span data-ttu-id="9b9e8-103">Задает имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="9b9e8-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b9e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b9e8-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="9b9e8-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9b9e8-105">Arguments</span></span>  
  
|<span data-ttu-id="9b9e8-106">Термин</span><span class="sxs-lookup"><span data-stu-id="9b9e8-106">Term</span></span>|<span data-ttu-id="9b9e8-107">Определение</span><span class="sxs-lookup"><span data-stu-id="9b9e8-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="9b9e8-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="9b9e8-108">Required.</span></span> <span data-ttu-id="9b9e8-109">Имя выходного файла, создаваемого компилятором.</span><span class="sxs-lookup"><span data-stu-id="9b9e8-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="9b9e8-110">Если имя файла содержит пробел, заключите его в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="9b9e8-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b9e8-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b9e8-111">Remarks</span></span>  
 <span data-ttu-id="9b9e8-112">Укажите полное имя и расширение создаваемого файла.</span><span class="sxs-lookup"><span data-stu-id="9b9e8-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="9b9e8-113">В противном случае exe-файл принимает имя из файла исходного кода, содержащего процедуру `Sub Main`, а DLL-файл принимает имя из первого файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="9b9e8-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="9b9e8-114">Если указать имя файла без расширения EXE или DLL, компилятор автоматически добавит расширение в зависимости от значения, указанного для параметра компилятора `-target`.</span><span class="sxs-lookup"><span data-stu-id="9b9e8-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="9b9e8-115">Установка в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9b9e8-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="9b9e8-116">1. Выберите проект в **Обозреватель решений**.</span><span class="sxs-lookup"><span data-stu-id="9b9e8-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="9b9e8-117">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9b9e8-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="9b9e8-118">2. Перейдите на вкладку **приложение** .</span><span class="sxs-lookup"><span data-stu-id="9b9e8-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="9b9e8-119">3. Измените значение в поле **имя сборки** .</span><span class="sxs-lookup"><span data-stu-id="9b9e8-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9b9e8-120">Пример</span><span class="sxs-lookup"><span data-stu-id="9b9e8-120">Example</span></span>  
 <span data-ttu-id="9b9e8-121">Следующий код компилирует `T2.vb` и создает выходной файл `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="9b9e8-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b9e8-122">См. также</span><span class="sxs-lookup"><span data-stu-id="9b9e8-122">See also</span></span>

- [<span data-ttu-id="9b9e8-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="9b9e8-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9b9e8-124">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b9e8-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="9b9e8-125">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="9b9e8-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
