---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 045e621f0104c4c958d77d2443c1524b33410b7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650469"
---
# <a name="-win32icon"></a><span data-ttu-id="55260-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="55260-102">-win32icon</span></span>
<span data-ttu-id="55260-103">Внедряет ICO-файл в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="55260-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="55260-104">ICO-файл представляет выходной файл в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="55260-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55260-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55260-105">Syntax</span></span>  
  
```  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="55260-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="55260-106">Arguments</span></span>  
  
|<span data-ttu-id="55260-107">Термин</span><span class="sxs-lookup"><span data-stu-id="55260-107">Term</span></span>|<span data-ttu-id="55260-108">Определение</span><span class="sxs-lookup"><span data-stu-id="55260-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="55260-109">Чтобы добавить в выходной файл ICO-файл.</span><span class="sxs-lookup"><span data-stu-id="55260-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="55260-110">Заключите имя файла в кавычки (» «), если он содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="55260-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55260-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="55260-111">Remarks</span></span>  
 <span data-ttu-id="55260-112">ICO-файл можно создать с помощью компилятора ресурсов Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="55260-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="55260-113">Компилятор ресурсов вызывается при компиляции программы Visual C++; ICO-файл создается из RC-файла.</span><span class="sxs-lookup"><span data-stu-id="55260-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="55260-114">`-win32icon` И `-win32resource` являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="55260-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="55260-115">В разделе [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) ссылку на [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов или [-ресурсов (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) для присоединения [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов.</span><span class="sxs-lookup"><span data-stu-id="55260-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span> <span data-ttu-id="55260-116">В разделе [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) Импорт RES-файл.</span><span class="sxs-lookup"><span data-stu-id="55260-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="55260-117">Чтобы задать - win32icon в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="55260-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="55260-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="55260-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="55260-119">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="55260-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="55260-120">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="55260-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="55260-121">3.  Измените значение в **значок** поле.</span><span class="sxs-lookup"><span data-stu-id="55260-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="55260-122">Пример</span><span class="sxs-lookup"><span data-stu-id="55260-122">Example</span></span>  
 <span data-ttu-id="55260-123">Следующий код компилирует `In.vb` и присоединяет ICO-файл `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="55260-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="55260-124">См. также</span><span class="sxs-lookup"><span data-stu-id="55260-124">See Also</span></span>  
 [<span data-ttu-id="55260-125">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="55260-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="55260-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="55260-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
