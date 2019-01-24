---
title: '&#39;Строки&#39; инструкции больше не поддерживаются (Ошибка компилятора Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 36226cc371ffb8a51cb8d0f918952f1c717aea10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702983"
---
# <a name="39line39-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="a533b-102">&#39;Строки&#39; инструкции больше не поддерживаются (Ошибка компилятора Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a533b-102">&#39;Line&#39; statements are no longer supported (Visual Basic Compiler Error)</span></span>
<span data-ttu-id="a533b-103">Операторы Line больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a533b-103">Line statements are no longer supported.</span></span> <span data-ttu-id="a533b-104">Функциональность файлового ввода-вывода доступна как `Microsoft.VisualBasic.FileSystem.LineInput` и графические функции доступен в виде `System.Drawing.Graphics.DrawLine`.</span><span class="sxs-lookup"><span data-stu-id="a533b-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="a533b-105">**Идентификатор ошибки:** BC30830</span><span class="sxs-lookup"><span data-stu-id="a533b-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a533b-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a533b-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="a533b-107">Если выполняется доступ к файлу, используйте `Microsoft.VisualBasic.FileSystem.LineInput`.</span><span class="sxs-lookup"><span data-stu-id="a533b-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2.  <span data-ttu-id="a533b-108">Если выполняется вывод графики, используйте `System.Drawing.Graphics.Drawline`.</span><span class="sxs-lookup"><span data-stu-id="a533b-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a533b-109">См. также</span><span class="sxs-lookup"><span data-stu-id="a533b-109">See also</span></span>
- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="a533b-110">Доступ к файлам с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a533b-110">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
