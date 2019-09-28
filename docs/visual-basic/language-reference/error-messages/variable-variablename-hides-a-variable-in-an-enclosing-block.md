---
title: Переменная <variablename> скрывает содержащуюся в блоке переменную
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 4312abef83728f432e2f6a492e5acad3450719b1
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592066"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="4cf6f-102">Переменная "\<variablename >" скрывает переменную во внешнем блоке</span><span class="sxs-lookup"><span data-stu-id="4cf6f-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="4cf6f-103">Переменная, заключенная в блок, имеет то же имя, что и другая локальная переменная.</span><span class="sxs-lookup"><span data-stu-id="4cf6f-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="4cf6f-104">**Идентификатор ошибки:** BC30616</span><span class="sxs-lookup"><span data-stu-id="4cf6f-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4cf6f-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4cf6f-105">To correct this error</span></span>  
  
- <span data-ttu-id="4cf6f-106">Переименуйте переменную во вложенном блоке так, чтобы она не совпадала с другими локальными переменными.</span><span class="sxs-lookup"><span data-stu-id="4cf6f-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="4cf6f-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="4cf6f-107">For example:</span></span>  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- <span data-ttu-id="4cf6f-108">Распространенной причиной этой ошибки является использование `Catch e As Exception` внутри обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="4cf6f-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="4cf6f-109">Если это так, присвойте переменной блока `Catch` `ex`, а не `e`.</span><span class="sxs-lookup"><span data-stu-id="4cf6f-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
- <span data-ttu-id="4cf6f-110">Другой распространенный источник этой ошибки — попытка доступа к локальной переменной, объявленной в блоке `Try`, в отдельном блоке `Catch`.</span><span class="sxs-lookup"><span data-stu-id="4cf6f-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="4cf6f-111">Чтобы исправить это, объявите переменную вне структуры `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="4cf6f-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf6f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4cf6f-112">See also</span></span>

- [<span data-ttu-id="4cf6f-113">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="4cf6f-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="4cf6f-114">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="4cf6f-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
