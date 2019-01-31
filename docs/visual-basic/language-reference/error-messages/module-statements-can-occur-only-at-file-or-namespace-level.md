---
title: Операторы Module могут присутствовать только на уровне файлов или пространств имен
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 0820763cce9cc27f9a379ed5e766e0691a75f36b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271269"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="90c1a-102">Операторы Module могут присутствовать только на уровне файлов или пространств имен</span><span class="sxs-lookup"><span data-stu-id="90c1a-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="90c1a-103">`Module` операторы должны находиться в начале файла исходного кода сразу же после `Option` и `Imports` инструкции, глобальных атрибутов и деклараций пространств имен, но перед всеми объявлениями.</span><span class="sxs-lookup"><span data-stu-id="90c1a-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="90c1a-104">**Идентификатор ошибки:** BC30617</span><span class="sxs-lookup"><span data-stu-id="90c1a-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="90c1a-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="90c1a-105">To correct this error</span></span>  
  
-   <span data-ttu-id="90c1a-106">Переместите оператор `Module` в начало объявления пространства имен или исходного файла.</span><span class="sxs-lookup"><span data-stu-id="90c1a-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c1a-107">См. также</span><span class="sxs-lookup"><span data-stu-id="90c1a-107">See also</span></span>
- [<span data-ttu-id="90c1a-108">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="90c1a-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
