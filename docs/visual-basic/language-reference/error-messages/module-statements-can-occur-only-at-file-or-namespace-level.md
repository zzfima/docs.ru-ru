---
title: '&#39;Модуль&#39; операторы могут использоваться только на уровне файлов и пространств имен'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 53199c2d7081445dc5490d5c54c98f93ee7522eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593169"
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="7cf11-102">&#39;Модуль&#39; операторы могут использоваться только на уровне файлов и пространств имен</span><span class="sxs-lookup"><span data-stu-id="7cf11-102">&#39;Module&#39; statements can occur only at file or namespace level</span></span>
<span data-ttu-id="7cf11-103">`Module` операторы должны находиться в верхней части файла исходного кода сразу после `Option` и `Imports` инструкции, глобальных атрибутов и объявлений пространств имен, но перед всеми остальными объявлениями.</span><span class="sxs-lookup"><span data-stu-id="7cf11-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="7cf11-104">**Идентификатор ошибки:** BC30617</span><span class="sxs-lookup"><span data-stu-id="7cf11-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7cf11-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7cf11-105">To correct this error</span></span>  
  
-   <span data-ttu-id="7cf11-106">Переместите `Module` в начало имен объявления или исходного файла.</span><span class="sxs-lookup"><span data-stu-id="7cf11-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf11-107">См. также</span><span class="sxs-lookup"><span data-stu-id="7cf11-107">See Also</span></span>  
 [<span data-ttu-id="7cf11-108">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="7cf11-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
