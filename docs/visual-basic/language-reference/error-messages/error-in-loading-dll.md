---
title: Ошибка при загрузке DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 36452cc6ff03042939cd4066aef76129b5bb8f0a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74329558"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="a7b41-102">Ошибка при загрузке библиотеки DLL (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7b41-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="a7b41-103">Библиотека динамической компоновки (DLL) — это библиотека, указанная в предложении `Lib` инструкции `Declare`.</span><span class="sxs-lookup"><span data-stu-id="a7b41-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="a7b41-104">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="a7b41-104">Possible causes for this error include:</span></span>  
  
- <span data-ttu-id="a7b41-105">Файл не является исполняемым файлом DLL.</span><span class="sxs-lookup"><span data-stu-id="a7b41-105">The file is not DLL executable.</span></span>  
  
- <span data-ttu-id="a7b41-106">Файл не является библиотекой Microsoft Windows DLL.</span><span class="sxs-lookup"><span data-stu-id="a7b41-106">The file is not a Microsoft Windows DLL.</span></span>  
  
- <span data-ttu-id="a7b41-107">Библиотека DLL ссылается на другую несуществующую библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="a7b41-107">The DLL references another DLL that is not present.</span></span>  
  
- <span data-ttu-id="a7b41-108">Библиотека DLL или библиотека DLL, на которую указывает ссылка, не находятся в каталоге, указанном в пути.</span><span class="sxs-lookup"><span data-stu-id="a7b41-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a7b41-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a7b41-109">To correct this error</span></span>  
  
- <span data-ttu-id="a7b41-110">Если файл является исходным текстовым файлом и, следовательно, не является исполняемым DLL-файлом, он должен быть скомпилирован и связан с исполняемой формой DLL.</span><span class="sxs-lookup"><span data-stu-id="a7b41-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
- <span data-ttu-id="a7b41-111">Если файл не является библиотекой Microsoft Windows DLL, получите эквивалент Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="a7b41-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
- <span data-ttu-id="a7b41-112">Если библиотека DLL ссылается на другую библиотеку DLL, которая отсутствует, получите указанную библиотеку DLL и сделайте ее доступной.</span><span class="sxs-lookup"><span data-stu-id="a7b41-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
- <span data-ttu-id="a7b41-113">Если библиотека DLL или библиотека DLL, на которую указывает ссылка, не находятся в каталоге, указанном в пути, переместите библиотеку DLL в каталог, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="a7b41-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b41-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a7b41-114">See also</span></span>

- [<span data-ttu-id="a7b41-115">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="a7b41-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
