---
title: Операторы Module могут присутствовать только на уровне файлов или пространств имен
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: bf0239422fb5a98e4670aea407f684753d3a7ea4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920865"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="e7505-102">Операторы Module могут присутствовать только на уровне файлов или пространств имен</span><span class="sxs-lookup"><span data-stu-id="e7505-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="e7505-103">`Module` операторы должны находиться в начале файла исходного кода сразу же после `Option` и `Imports` инструкции, глобальных атрибутов и деклараций пространств имен, но перед всеми объявлениями.</span><span class="sxs-lookup"><span data-stu-id="e7505-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="e7505-104">**Идентификатор ошибки:** BC30617</span><span class="sxs-lookup"><span data-stu-id="e7505-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e7505-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e7505-105">To correct this error</span></span>  
  
- <span data-ttu-id="e7505-106">Переместите оператор `Module` в начало объявления пространства имен или исходного файла.</span><span class="sxs-lookup"><span data-stu-id="e7505-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7505-107">См. также</span><span class="sxs-lookup"><span data-stu-id="e7505-107">See also</span></span>

- [<span data-ttu-id="e7505-108">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="e7505-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
