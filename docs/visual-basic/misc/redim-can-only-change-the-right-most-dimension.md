---
title: "&#39; ReDim &#39; можно изменять только крайнее правое измерение"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 989a06f94824dfd051d1a7d2e7749dbb8c8e11a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="e38fa-102">&#39; ReDim &#39; можно изменять только крайнее правое измерение</span><span class="sxs-lookup"><span data-stu-id="e38fa-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="e38fa-103">В операторе `ReDim` ключевое слово `Preserve` используется для изменения измерения массива, которое не является его последним измерением.</span><span class="sxs-lookup"><span data-stu-id="e38fa-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="e38fa-104">При использовании `Preserve`можно изменять размер только последнего измерения массива.</span><span class="sxs-lookup"><span data-stu-id="e38fa-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="e38fa-105">Для всех других измерений необходимо указать тот же размер, что и для существующего массива.</span><span class="sxs-lookup"><span data-stu-id="e38fa-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e38fa-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e38fa-106">To correct this error</span></span>  
  
-   <span data-ttu-id="e38fa-107">Удалите ключевое слово `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="e38fa-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e38fa-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e38fa-108">See Also</span></span>  
 [<span data-ttu-id="e38fa-109">Массивы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e38fa-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="e38fa-110">Размерности массивов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e38fa-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="e38fa-111">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="e38fa-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="e38fa-112">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="e38fa-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="e38fa-113">Preserve — удалить</span><span class="sxs-lookup"><span data-stu-id="e38fa-113">Preserve - delete</span></span>](http://msdn.microsoft.com/en-us/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
