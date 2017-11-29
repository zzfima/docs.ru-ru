---
title: /win32icon
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65149c617220966bc3bb6897d757a71cd60167d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="win32icon"></a><span data-ttu-id="1c397-102">/win32icon</span><span class="sxs-lookup"><span data-stu-id="1c397-102">/win32icon</span></span>
<span data-ttu-id="1c397-103">Внедряет ICO-файл в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="1c397-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="1c397-104">ICO-файл представляет выходной файл в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="1c397-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c397-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c397-105">Syntax</span></span>  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="1c397-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1c397-106">Arguments</span></span>  
  
|<span data-ttu-id="1c397-107">Термин</span><span class="sxs-lookup"><span data-stu-id="1c397-107">Term</span></span>|<span data-ttu-id="1c397-108">Определение</span><span class="sxs-lookup"><span data-stu-id="1c397-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="1c397-109">Чтобы добавить в выходной файл ICO-файл.</span><span class="sxs-lookup"><span data-stu-id="1c397-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="1c397-110">Заключите имя файла в кавычки (» «), если он содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="1c397-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c397-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1c397-111">Remarks</span></span>  
 <span data-ttu-id="1c397-112">ICO-файл можно создать с помощью компилятора ресурсов Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="1c397-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="1c397-113">Компилятор ресурсов вызывается при компиляции программы Visual C++; ICO-файл создается из RC-файла.</span><span class="sxs-lookup"><span data-stu-id="1c397-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="1c397-114">`/win32icon` И `/win32resource` являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="1c397-114">The `/win32icon` and `/win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="1c397-115">В разделе [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) ссылка [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов или [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) для присоединения [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1c397-115">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span> <span data-ttu-id="1c397-116">В разделе [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) Импорт RES-файл.</span><span class="sxs-lookup"><span data-stu-id="1c397-116">See [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="1c397-117">Чтобы задать/win32icon в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1c397-117">To set /win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="1c397-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="1c397-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1c397-119">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1c397-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="1c397-120">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="1c397-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="1c397-121">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="1c397-121">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="1c397-122">3.  Измените значение в **значок** поле.</span><span class="sxs-lookup"><span data-stu-id="1c397-122">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1c397-123">Пример</span><span class="sxs-lookup"><span data-stu-id="1c397-123">Example</span></span>  
 <span data-ttu-id="1c397-124">Следующий код компилирует `In.vb` и присоединяет ICO-файл `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="1c397-124">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c397-125">См. также</span><span class="sxs-lookup"><span data-stu-id="1c397-125">See Also</span></span>  
 [<span data-ttu-id="1c397-126">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="1c397-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1c397-127">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="1c397-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
