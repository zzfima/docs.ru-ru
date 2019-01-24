---
title: '&#39;Модуль&#39; операторы могут использоваться только на уровне файлов или пространств имен'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: bdbf8df5942e9df4b9696aeea4e3492121efe21a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746316"
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="c6c16-102">&#39;Модуль&#39; операторы могут использоваться только на уровне файлов или пространств имен</span><span class="sxs-lookup"><span data-stu-id="c6c16-102">&#39;Module&#39; statements can occur only at file or namespace level</span></span>
<span data-ttu-id="c6c16-103">`Module` операторы должны находиться в начале файла исходного кода сразу же после `Option` и `Imports` инструкции, глобальных атрибутов и деклараций пространств имен, но перед всеми объявлениями.</span><span class="sxs-lookup"><span data-stu-id="c6c16-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="c6c16-104">**Идентификатор ошибки:** BC30617</span><span class="sxs-lookup"><span data-stu-id="c6c16-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c6c16-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c6c16-105">To correct this error</span></span>  
  
-   <span data-ttu-id="c6c16-106">Переместите оператор `Module` в начало объявления пространства имен или исходного файла.</span><span class="sxs-lookup"><span data-stu-id="c6c16-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c16-107">См. также</span><span class="sxs-lookup"><span data-stu-id="c6c16-107">See also</span></span>
- [<span data-ttu-id="c6c16-108">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="c6c16-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
