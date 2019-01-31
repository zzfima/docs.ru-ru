---
title: Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 17025e9a3c87d84a10ddaa7aeef616d985143879
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283239"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="2600d-102">Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2600d-102">'Line' statements are no longer supported (Visual Basic Compiler Error)</span></span>
<span data-ttu-id="2600d-103">Операторы Line больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="2600d-103">Line statements are no longer supported.</span></span> <span data-ttu-id="2600d-104">Функциональность файлового ввода-вывода доступна как `Microsoft.VisualBasic.FileSystem.LineInput` и графические функции доступен в виде `System.Drawing.Graphics.DrawLine`.</span><span class="sxs-lookup"><span data-stu-id="2600d-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="2600d-105">**Идентификатор ошибки:** BC30830</span><span class="sxs-lookup"><span data-stu-id="2600d-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2600d-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2600d-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="2600d-107">Если выполняется доступ к файлу, используйте `Microsoft.VisualBasic.FileSystem.LineInput`.</span><span class="sxs-lookup"><span data-stu-id="2600d-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2.  <span data-ttu-id="2600d-108">Если выполняется вывод графики, используйте `System.Drawing.Graphics.Drawline`.</span><span class="sxs-lookup"><span data-stu-id="2600d-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2600d-109">См. также</span><span class="sxs-lookup"><span data-stu-id="2600d-109">See also</span></span>
- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="2600d-110">Доступ к файлам с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2600d-110">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
