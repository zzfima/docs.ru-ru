---
title: '&#39;#Region&#39; и &#39;#End Region&#39; недопустимы в метод тел многострочного лямбда-выражения'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: bf3843e0ec3009f3dc7d60e91c340a7f20543231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="8d862-102">&#39;#Region&#39; и &#39;#End Region&#39; недопустимы в телах/многострочной лямбде метод</span><span class="sxs-lookup"><span data-stu-id="8d862-102">&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="8d862-103">`#Region` Блок должен быть объявлен на уровне класса, модуля или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8d862-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="8d862-104">Сворачиваемой области может включать один или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="8d862-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="8d862-105">**Идентификатор ошибки:** BC32025</span><span class="sxs-lookup"><span data-stu-id="8d862-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8d862-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="8d862-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="8d862-107">Убедитесь, что и предыдущая процедура завершается должным образом с `End Function` или `End Sub` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8d862-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="8d862-108">Убедитесь, что `#Region` и `#End Region` директивы находятся в одном блоке кода.</span><span class="sxs-lookup"><span data-stu-id="8d862-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d862-109">См. также</span><span class="sxs-lookup"><span data-stu-id="8d862-109">See Also</span></span>  
 [<span data-ttu-id="8d862-110">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="8d862-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
