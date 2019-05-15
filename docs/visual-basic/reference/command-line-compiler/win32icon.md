---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: dc48a8f79aa04892c514917da00b8fd6489695b1
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593088"
---
# <a name="-win32icon"></a><span data-ttu-id="63720-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="63720-102">-win32icon</span></span>
<span data-ttu-id="63720-103">Вставляет ICO-файл в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="63720-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="63720-104">Этот ICO-файл представляет выходной файл в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="63720-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63720-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63720-105">Syntax</span></span>  
  
```  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="63720-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="63720-106">Arguments</span></span>  
  
|<span data-ttu-id="63720-107">Термин</span><span class="sxs-lookup"><span data-stu-id="63720-107">Term</span></span>|<span data-ttu-id="63720-108">Определение</span><span class="sxs-lookup"><span data-stu-id="63720-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="63720-109">Чтобы добавить в выходной файл ICO-файл.</span><span class="sxs-lookup"><span data-stu-id="63720-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="63720-110">Заключите имя файла в кавычки (» «), если он содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="63720-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63720-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="63720-111">Remarks</span></span>  
 <span data-ttu-id="63720-112">ICO-файл можно создать с помощью компилятора ресурсов Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="63720-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="63720-113">Компилятор ресурсов вызывается при компиляции программы Visual C++; ICO-файл создается из RC-файл.</span><span class="sxs-lookup"><span data-stu-id="63720-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="63720-114">`-win32icon` И `-win32resource` параметры являются взаимно исключающими.</span><span class="sxs-lookup"><span data-stu-id="63720-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="63720-115">См. в разделе [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) для ссылки на файл ресурсов .NET Framework или [-ресурсов (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) вложить файл ресурсов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="63720-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="63720-116">См. в разделе [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) для импорта RES-файл.</span><span class="sxs-lookup"><span data-stu-id="63720-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="63720-117">Чтобы задать - win32icon в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63720-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="63720-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="63720-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="63720-119">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="63720-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="63720-120">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="63720-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="63720-121">3.  Измените значение в **значок** поле.</span><span class="sxs-lookup"><span data-stu-id="63720-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="63720-122">Пример</span><span class="sxs-lookup"><span data-stu-id="63720-122">Example</span></span>  
 <span data-ttu-id="63720-123">Следующий код компилирует `In.vb` и присоединяет ICO-файл, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="63720-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="63720-124">См. также</span><span class="sxs-lookup"><span data-stu-id="63720-124">See also</span></span>

- [<span data-ttu-id="63720-125">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="63720-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="63720-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="63720-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
