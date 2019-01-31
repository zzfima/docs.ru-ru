---
title: Функция Dir должна первый раз вызываться с аргументом PathName
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 828c715d9aaceef17d030113e7eda302f025ca9d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282598"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="9d913-102">Функция Dir должна первый раз вызываться с аргументом PathName</span><span class="sxs-lookup"><span data-stu-id="9d913-102">'Dir' function must first be called with a 'PathName' argument</span></span>
<span data-ttu-id="9d913-103">Исходный вызов `Dir` функция не поддерживает `PathName` аргумент.</span><span class="sxs-lookup"><span data-stu-id="9d913-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="9d913-104">Первый вызов `Dir` должен включать `PathName`, но последующие вызовы `Dir` не обязательно должны включать параметры для извлечения следующего элемента.</span><span class="sxs-lookup"><span data-stu-id="9d913-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9d913-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9d913-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="9d913-106">Укажите `PathName` аргумента в вызове функции.</span><span class="sxs-lookup"><span data-stu-id="9d913-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d913-107">См. также</span><span class="sxs-lookup"><span data-stu-id="9d913-107">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
