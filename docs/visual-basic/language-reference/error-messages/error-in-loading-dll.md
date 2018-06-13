---
title: Ошибка при загрузке библиотеки DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: ac21c4d52b248025ee26bac3e511bb5b0a0b668e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584687"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="d332f-102">Ошибка при загрузке библиотеки DLL (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d332f-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="d332f-103">Библиотеки динамической компоновки (DLL) — это библиотека, указанный в `Lib` предложения `Declare` инструкции.</span><span class="sxs-lookup"><span data-stu-id="d332f-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="d332f-104">Среди возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="d332f-104">Possible causes for this error include:</span></span>  
  
-   <span data-ttu-id="d332f-105">Файл не является исполняемой программой DLL.</span><span class="sxs-lookup"><span data-stu-id="d332f-105">The file is not DLL executable.</span></span>  
  
-   <span data-ttu-id="d332f-106">Файл не является Библиотекой Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="d332f-106">The file is not a Microsoft Windows DLL.</span></span>  
  
-   <span data-ttu-id="d332f-107">DLL ссылается на другой библиотеке DLL, не существует.</span><span class="sxs-lookup"><span data-stu-id="d332f-107">The DLL references another DLL that is not present.</span></span>  
  
-   <span data-ttu-id="d332f-108">DLL или DLL, на которую указывает ссылка не находится в каталоге, указанном в пути.</span><span class="sxs-lookup"><span data-stu-id="d332f-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d332f-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d332f-109">To correct this error</span></span>  
  
-   <span data-ttu-id="d332f-110">Если файл исходного текста файла и поэтому не исполняемым файлом DLL, ее необходимо компиляции и компоновки в форму исполняемого файла DLL.</span><span class="sxs-lookup"><span data-stu-id="d332f-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
-   <span data-ttu-id="d332f-111">Если файл не является Библиотекой Microsoft Windows, получите эквивалентное Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="d332f-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
-   <span data-ttu-id="d332f-112">Если DLL ссылается на другой библиотеки DLL, которая не указан, получите указанной библиотеке DLL и сделать ее доступной.</span><span class="sxs-lookup"><span data-stu-id="d332f-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
-   <span data-ttu-id="d332f-113">Если DLL или DLL, на которую указывает ссылка не находится в каталоге, указанном в пути, следует перенести DLL к указанному каталогу.</span><span class="sxs-lookup"><span data-stu-id="d332f-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d332f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d332f-114">See Also</span></span>  
 [<span data-ttu-id="d332f-115">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="d332f-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
