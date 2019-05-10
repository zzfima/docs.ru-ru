---
title: Операторы Module могут присутствовать только на уровне файлов или пространств имен
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: fc3c102dbfe7c55e66093421bc11379d48ba000d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592095"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="f1951-102">Операторы Module могут присутствовать только на уровне файлов или пространств имен</span><span class="sxs-lookup"><span data-stu-id="f1951-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="f1951-103">`Module` операторы должны находиться в начале файла исходного кода сразу же после `Option` и `Imports` инструкции, глобальных атрибутов и деклараций пространств имен, но перед всеми объявлениями.</span><span class="sxs-lookup"><span data-stu-id="f1951-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="f1951-104">**Идентификатор ошибки:** BC30617</span><span class="sxs-lookup"><span data-stu-id="f1951-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f1951-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f1951-105">To correct this error</span></span>  
  
- <span data-ttu-id="f1951-106">Переместите оператор `Module` в начало объявления пространства имен или исходного файла.</span><span class="sxs-lookup"><span data-stu-id="f1951-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1951-107">См. также</span><span class="sxs-lookup"><span data-stu-id="f1951-107">See also</span></span>

- [<span data-ttu-id="f1951-108">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="f1951-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
