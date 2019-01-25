---
title: Ошибка при загрузке библиотеки DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 76a0a443fd9f8a6dec5ead24bc75c97d89d6c36b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518466"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="c57c1-102">Ошибка при загрузке библиотеки DLL (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c57c1-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="c57c1-103">Это библиотека динамической компоновки (DLL) — это библиотека, указанный в `Lib` предложении `Declare` инструкции.</span><span class="sxs-lookup"><span data-stu-id="c57c1-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="c57c1-104">Среди возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="c57c1-104">Possible causes for this error include:</span></span>  
  
-   <span data-ttu-id="c57c1-105">Файл не является исполняемой программой DLL.</span><span class="sxs-lookup"><span data-stu-id="c57c1-105">The file is not DLL executable.</span></span>  
  
-   <span data-ttu-id="c57c1-106">Файл не является Библиотекой Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="c57c1-106">The file is not a Microsoft Windows DLL.</span></span>  
  
-   <span data-ttu-id="c57c1-107">DLL ссылается на другой библиотеке DLL, не существует.</span><span class="sxs-lookup"><span data-stu-id="c57c1-107">The DLL references another DLL that is not present.</span></span>  
  
-   <span data-ttu-id="c57c1-108">DLL или DLL, на которую указывает ссылка отсутствует в каталоге, указанном в пути.</span><span class="sxs-lookup"><span data-stu-id="c57c1-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c57c1-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c57c1-109">To correct this error</span></span>  
  
-   <span data-ttu-id="c57c1-110">Если файл источника текстовый файл и поэтому не исполняемый файл DLL, он должен будет компилироваться и собираться в форму исполняемого файла DLL.</span><span class="sxs-lookup"><span data-stu-id="c57c1-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
-   <span data-ttu-id="c57c1-111">Если файл не является Библиотекой Microsoft Windows, получите эквивалентное Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="c57c1-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
-   <span data-ttu-id="c57c1-112">Если библиотека DLL ссылается другая библиотека DLL, которая отсутствует, получите указанной библиотеке DLL и сделать его доступным.</span><span class="sxs-lookup"><span data-stu-id="c57c1-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
-   <span data-ttu-id="c57c1-113">Если DLL или DLL, на которую указывает ссылка не находится в каталоге, указанном в пути, переместите библиотеку DLL в каталог, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="c57c1-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c57c1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c57c1-114">See also</span></span>
- [<span data-ttu-id="c57c1-115">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="c57c1-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
