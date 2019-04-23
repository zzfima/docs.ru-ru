---
title: Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: c7a3e6bcd0db268a0e0acfc74c570e26f89cff6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339077"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="e55cb-102">Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e55cb-102">'Line' statements are no longer supported (Visual Basic Compiler Error)</span></span>
<span data-ttu-id="e55cb-103">Операторы Line больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e55cb-103">Line statements are no longer supported.</span></span> <span data-ttu-id="e55cb-104">Функциональность файлового ввода-вывода доступна как `Microsoft.VisualBasic.FileSystem.LineInput` и графические функции доступен в виде `System.Drawing.Graphics.DrawLine`.</span><span class="sxs-lookup"><span data-stu-id="e55cb-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="e55cb-105">**Идентификатор ошибки:** BC30830</span><span class="sxs-lookup"><span data-stu-id="e55cb-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e55cb-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e55cb-106">To correct this error</span></span>  
  
1. <span data-ttu-id="e55cb-107">Если выполняется доступ к файлу, используйте `Microsoft.VisualBasic.FileSystem.LineInput`.</span><span class="sxs-lookup"><span data-stu-id="e55cb-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2. <span data-ttu-id="e55cb-108">Если выполняется вывод графики, используйте `System.Drawing.Graphics.Drawline`.</span><span class="sxs-lookup"><span data-stu-id="e55cb-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e55cb-109">См. также</span><span class="sxs-lookup"><span data-stu-id="e55cb-109">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="e55cb-110">Доступ к файлам с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e55cb-110">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
