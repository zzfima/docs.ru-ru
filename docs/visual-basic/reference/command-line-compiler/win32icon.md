---
title: "/ win32icon | Документы Microsoft"
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
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: 13
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
ms.openlocfilehash: f7d451026438be722d6cb7eecfffe397ccff82ae
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="win32icon"></a><span data-ttu-id="b2794-102">/win32icon</span><span class="sxs-lookup"><span data-stu-id="b2794-102">/win32icon</span></span>
<span data-ttu-id="b2794-103">Внедряет ICO-файл в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="b2794-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="b2794-104">Файл ICO представляет выходной файл в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="b2794-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2794-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2794-105">Syntax</span></span>  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="b2794-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b2794-106">Arguments</span></span>  
  
|<span data-ttu-id="b2794-107">Термин</span><span class="sxs-lookup"><span data-stu-id="b2794-107">Term</span></span>|<span data-ttu-id="b2794-108">Определение</span><span class="sxs-lookup"><span data-stu-id="b2794-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="b2794-109">Добавить в выходной файл ICO-файл.</span><span class="sxs-lookup"><span data-stu-id="b2794-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="b2794-110">Заключите имя файла в кавычки («»), если он содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="b2794-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2794-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2794-111">Remarks</span></span>  
 <span data-ttu-id="b2794-112">ICO-файл можно создать с помощью компилятора ресурсов Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="b2794-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="b2794-113">Компилятор ресурсов вызывается при компиляции программы Visual C++; ICO-файл создается из RC-файла.</span><span class="sxs-lookup"><span data-stu-id="b2794-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="b2794-114">`/win32icon` И `/win32resource` являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="b2794-114">The `/win32icon` and `/win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="b2794-115">В разделе [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) ссылка [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] файл ресурсов или [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) присоединить [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] файла ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b2794-115">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file.</span></span> <span data-ttu-id="b2794-116">В разделе [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) Импорт RES-файл.</span><span class="sxs-lookup"><span data-stu-id="b2794-116">See [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="b2794-117">Установка/win32icon в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b2794-117">To set /win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="b2794-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="b2794-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b2794-119">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="b2794-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="b2794-120">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="b2794-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="b2794-121">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="b2794-121">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="b2794-122">3.  Измените значение в **значок** поле.</span><span class="sxs-lookup"><span data-stu-id="b2794-122">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2794-123">Пример</span><span class="sxs-lookup"><span data-stu-id="b2794-123">Example</span></span>  
 <span data-ttu-id="b2794-124">Следующий код компилирует `In.vb` и присоединяется файл ICO `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="b2794-124">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2794-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b2794-125">See Also</span></span>  
 <span data-ttu-id="b2794-126">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="b2794-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="b2794-127"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="b2794-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
