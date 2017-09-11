---
title: "Модули (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- modules, Visual Basic
ms.assetid: 370bfc90-e8f2-4942-bdec-9897ce605d31
caps.latest.revision: 11
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
ms.openlocfilehash: 808510c83339e1768dba39f119a2e97ac44f0e4a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="modules-visual-basic"></a><span data-ttu-id="a51ec-102">Модули (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a51ec-102">Modules (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="a51ec-103">предоставляет несколько модулей, позволяющих упростить общие задачи в коде, включая работу со строками, математические вычисления, получение системной информации, операции с файлами и каталогами и т. д.</span><span class="sxs-lookup"><span data-stu-id="a51ec-103"> provides several modules that enable you to simplify common tasks in your code, including manipulating strings, performing mathematical calculations, getting system information, performing file and directory operations, and so on.</span></span> <span data-ttu-id="a51ec-104">В следующей таблице перечислены модули, предоставляемые [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="a51ec-104">The following table lists the modules provided by [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="a51ec-105"><xref:Microsoft.VisualBasic.Constants></xref:Microsoft.VisualBasic.Constants></span><span class="sxs-lookup"><span data-stu-id="a51ec-105"><xref:Microsoft.VisualBasic.Constants></span></span>|<span data-ttu-id="a51ec-106">Содержит различные константы.</span><span class="sxs-lookup"><span data-stu-id="a51ec-106">Contains miscellaneous constants.</span></span> <span data-ttu-id="a51ec-107">Эти константы можно использовать в любом месте в коде.</span><span class="sxs-lookup"><span data-stu-id="a51ec-107">These constants can be used anywhere in your code.</span></span>|  
|<span data-ttu-id="a51ec-108"><xref:Microsoft.VisualBasic.ControlChars></xref:Microsoft.VisualBasic.ControlChars></span><span class="sxs-lookup"><span data-stu-id="a51ec-108"><xref:Microsoft.VisualBasic.ControlChars></span></span>|<span data-ttu-id="a51ec-109">Содержит константные управляющие символы для печати и отображения текста.</span><span class="sxs-lookup"><span data-stu-id="a51ec-109">Contains constant control characters for printing and displaying text.</span></span>|  
|<span data-ttu-id="a51ec-110"><xref:Microsoft.VisualBasic.Conversion></xref:Microsoft.VisualBasic.Conversion></span><span class="sxs-lookup"><span data-stu-id="a51ec-110"><xref:Microsoft.VisualBasic.Conversion></span></span>|<span data-ttu-id="a51ec-111">Содержит элементы, которые преобразования десятичных чисел в другие системы счисления, чисел в строки, строк в числа и одного типа к другому.</span><span class="sxs-lookup"><span data-stu-id="a51ec-111">Contains members that convert decimal numbers to other bases, numbers to strings, strings to numbers, and one data type to another.</span></span>|  
|<span data-ttu-id="a51ec-112"><xref:Microsoft.VisualBasic.DateAndTime></xref:Microsoft.VisualBasic.DateAndTime></span><span class="sxs-lookup"><span data-stu-id="a51ec-112"><xref:Microsoft.VisualBasic.DateAndTime></span></span>|<span data-ttu-id="a51ec-113">Содержит элементы, которые получают текущую дату или время, вычисляют дату, возвращают дату или время длительности процесса.</span><span class="sxs-lookup"><span data-stu-id="a51ec-113">Contains members that get the current date or time, perform date calculations, return a date or time, set the date or time, or time the duration of a process.</span></span>|  
|<span data-ttu-id="a51ec-114"><xref:Microsoft.VisualBasic.ErrObject></xref:Microsoft.VisualBasic.ErrObject></span><span class="sxs-lookup"><span data-stu-id="a51ec-114"><xref:Microsoft.VisualBasic.ErrObject></span></span>|<span data-ttu-id="a51ec-115">Содержит сведения о методах создания или устранения ошибки и ошибки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a51ec-115">Contains information about run-time errors and methods to raise or clear an error.</span></span>|  
|<span data-ttu-id="a51ec-116"><xref:Microsoft.VisualBasic.FileSystem></xref:Microsoft.VisualBasic.FileSystem></span><span class="sxs-lookup"><span data-stu-id="a51ec-116"><xref:Microsoft.VisualBasic.FileSystem></span></span>|<span data-ttu-id="a51ec-117">Содержит элементы, выполняющие операции файла, каталога или папки и системы.</span><span class="sxs-lookup"><span data-stu-id="a51ec-117">Contains members that perform file, directory or folder, and system operations.</span></span>|  
|<span data-ttu-id="a51ec-118"><xref:Microsoft.VisualBasic.Financial></xref:Microsoft.VisualBasic.Financial></span><span class="sxs-lookup"><span data-stu-id="a51ec-118"><xref:Microsoft.VisualBasic.Financial></span></span>|<span data-ttu-id="a51ec-119">Содержит процедуры, используемые для выполнения финансовых вычислений.</span><span class="sxs-lookup"><span data-stu-id="a51ec-119">Contains procedures that are used to perform financial calculations.</span></span>|  
|<span data-ttu-id="a51ec-120"><xref:Microsoft.VisualBasic.Globals></xref:Microsoft.VisualBasic.Globals></span><span class="sxs-lookup"><span data-stu-id="a51ec-120"><xref:Microsoft.VisualBasic.Globals></span></span>|<span data-ttu-id="a51ec-121">Содержит сведения о текущей версии обработчика скриптов.</span><span class="sxs-lookup"><span data-stu-id="a51ec-121">Contains information about the current scripting engine version.</span></span>|  
|<span data-ttu-id="a51ec-122"><xref:Microsoft.VisualBasic.Information></xref:Microsoft.VisualBasic.Information></span><span class="sxs-lookup"><span data-stu-id="a51ec-122"><xref:Microsoft.VisualBasic.Information></span></span>|<span data-ttu-id="a51ec-123">Содержит элементы, которые возвращают, проверки или проверьте сведения, такие как размер массива, имена типов и т. д.</span><span class="sxs-lookup"><span data-stu-id="a51ec-123">Contains the members that return, test for, or verify information such as array size, type names, and so on.</span></span>|  
|<span data-ttu-id="a51ec-124"><xref:Microsoft.VisualBasic.Interaction></xref:Microsoft.VisualBasic.Interaction></span><span class="sxs-lookup"><span data-stu-id="a51ec-124"><xref:Microsoft.VisualBasic.Interaction></span></span>|<span data-ttu-id="a51ec-125">Содержит элементы, взаимодействующие с объектами, приложениями и системами.</span><span class="sxs-lookup"><span data-stu-id="a51ec-125">Contains members interact with objects, applications, and systems.</span></span>|  
|<span data-ttu-id="a51ec-126"><xref:Microsoft.VisualBasic.Strings></xref:Microsoft.VisualBasic.Strings></span><span class="sxs-lookup"><span data-stu-id="a51ec-126"><xref:Microsoft.VisualBasic.Strings></span></span>|<span data-ttu-id="a51ec-127">Содержит элементы, выполнения операций над строками, например переформатирование строк, поиск строки, получение длины строки и т. д.</span><span class="sxs-lookup"><span data-stu-id="a51ec-127">Contains members that perform string operations such as reformatting strings, searching a string, getting the length of a string, and so on.</span></span>|  
|<span data-ttu-id="a51ec-128"><xref:Microsoft.VisualBasic.VBMath></xref:Microsoft.VisualBasic.VBMath></span><span class="sxs-lookup"><span data-stu-id="a51ec-128"><xref:Microsoft.VisualBasic.VBMath></span></span>|<span data-ttu-id="a51ec-129">Содержит элементы для выполнения математических операций.</span><span class="sxs-lookup"><span data-stu-id="a51ec-129">Contains members perform mathematical operations.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a51ec-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a51ec-130">See Also</span></span>  
 <span data-ttu-id="a51ec-131">[Справочник по языку Visual Basic](../../visual-basic/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a51ec-131">[Visual Basic Language Reference](../../visual-basic/language-reference/index.md) </span></span>  
<span data-ttu-id="a51ec-132"> [Visual Basic](../../visual-basic/index.md)</span><span class="sxs-lookup"><span data-stu-id="a51ec-132"> [Visual Basic](../../visual-basic/index.md)</span></span>
