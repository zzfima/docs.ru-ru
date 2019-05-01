---
title: Операторы «#Region» и «#End Region» недопустимы в телах / многострочной лямбды метод
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: c41b95da7e3565ae7aaf332fe49361336e79f7c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013768"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="3733c-102">Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах</span><span class="sxs-lookup"><span data-stu-id="3733c-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="3733c-103">`#Region` Блок должен быть объявлен на уровне класса, модуля или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="3733c-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="3733c-104">Сворачиваемую область может включать один или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="3733c-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="3733c-105">**Идентификатор ошибки:** BC32025</span><span class="sxs-lookup"><span data-stu-id="3733c-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3733c-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="3733c-106">To correct this error</span></span>  
  
1. <span data-ttu-id="3733c-107">Убедитесь, что предыдущая процедура завершается должным образом с `End Function` или `End Sub` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3733c-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="3733c-108">Убедитесь, что `#Region` и `#End Region` директивы находятся в одном блоке кода.</span><span class="sxs-lookup"><span data-stu-id="3733c-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3733c-109">См. также</span><span class="sxs-lookup"><span data-stu-id="3733c-109">See also</span></span>

- [<span data-ttu-id="3733c-110">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="3733c-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
