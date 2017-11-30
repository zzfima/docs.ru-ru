---
title: "Ошибка при загрузке библиотеки DLL (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cc557dcc6709178b6519adb56f31debcbd1d1c39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="2417a-102">Ошибка при загрузке библиотеки DLL (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2417a-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="2417a-103">Библиотеки динамической компоновки (DLL) — это библиотека, указанный в `Lib` предложения `Declare` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2417a-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="2417a-104">Среди возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="2417a-104">Possible causes for this error include:</span></span>  
  
-   <span data-ttu-id="2417a-105">Файл не является исполняемой программой DLL.</span><span class="sxs-lookup"><span data-stu-id="2417a-105">The file is not DLL executable.</span></span>  
  
-   <span data-ttu-id="2417a-106">Файл не является Библиотекой Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="2417a-106">The file is not a Microsoft Windows DLL.</span></span>  
  
-   <span data-ttu-id="2417a-107">DLL ссылается на другой библиотеке DLL, не существует.</span><span class="sxs-lookup"><span data-stu-id="2417a-107">The DLL references another DLL that is not present.</span></span>  
  
-   <span data-ttu-id="2417a-108">DLL или DLL, на которую указывает ссылка не находится в каталоге, указанном в пути.</span><span class="sxs-lookup"><span data-stu-id="2417a-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2417a-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2417a-109">To correct this error</span></span>  
  
-   <span data-ttu-id="2417a-110">Если файл исходного текста файла и поэтому не исполняемым файлом DLL, ее необходимо компиляции и компоновки в форму исполняемого файла DLL.</span><span class="sxs-lookup"><span data-stu-id="2417a-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
-   <span data-ttu-id="2417a-111">Если файл не является Библиотекой Microsoft Windows, получите эквивалентное Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="2417a-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
-   <span data-ttu-id="2417a-112">Если DLL ссылается на другой библиотеки DLL, которая не указан, получите указанной библиотеке DLL и сделать ее доступной.</span><span class="sxs-lookup"><span data-stu-id="2417a-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
-   <span data-ttu-id="2417a-113">Если DLL или DLL, на которую указывает ссылка не находится в каталоге, указанном в пути, следует перенести DLL к указанному каталогу.</span><span class="sxs-lookup"><span data-stu-id="2417a-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2417a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2417a-114">See Also</span></span>  
 [<span data-ttu-id="2417a-115">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="2417a-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
