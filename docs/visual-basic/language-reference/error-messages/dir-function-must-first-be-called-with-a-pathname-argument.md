---
title: '&#39;Dir&#39; функция сначала должен вызываться с &#39;PathName&#39; аргумент'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: f7e9ef9cc6309f24ae9f8963e910b41180c029b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518492"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a><span data-ttu-id="41a5b-102">&#39;Dir&#39; функция сначала должен вызываться с &#39;PathName&#39; аргумент</span><span class="sxs-lookup"><span data-stu-id="41a5b-102">&#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument</span></span>
<span data-ttu-id="41a5b-103">Исходный вызов `Dir` функция не поддерживает `PathName` аргумент.</span><span class="sxs-lookup"><span data-stu-id="41a5b-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="41a5b-104">Первый вызов `Dir` должен включать `PathName`, но последующие вызовы `Dir` не обязательно должны включать параметры для извлечения следующего элемента.</span><span class="sxs-lookup"><span data-stu-id="41a5b-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="41a5b-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="41a5b-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="41a5b-106">Укажите `PathName` аргумента в вызове функции.</span><span class="sxs-lookup"><span data-stu-id="41a5b-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a5b-107">См. также</span><span class="sxs-lookup"><span data-stu-id="41a5b-107">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
