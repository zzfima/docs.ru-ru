---
title: "Переменная &#39; &lt;variablename&gt;&#39; скрывает переменную во внешнем блоке"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords: BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2af570cd002b4be4e15a7c03b0ffc2ff84ba3982
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="03c84-102">Переменная &#39; &lt;variablename&gt;&#39; скрывает переменную во внешнем блоке</span><span class="sxs-lookup"><span data-stu-id="03c84-102">Variable &#39;&lt;variablename&gt;&#39; hides a variable in an enclosing block</span></span>
<span data-ttu-id="03c84-103">Переменная, заключенном в блоке имеет имя, совпадающее с именем другой локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="03c84-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="03c84-104">**Идентификатор ошибки:** BC30616</span><span class="sxs-lookup"><span data-stu-id="03c84-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03c84-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="03c84-105">To correct this error</span></span>  
  
-   <span data-ttu-id="03c84-106">Переименуйте переменную, содержащуюся в блоке, чтобы это не то же, что локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="03c84-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="03c84-107">Например:</span><span class="sxs-lookup"><span data-stu-id="03c84-107">For example:</span></span>  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   <span data-ttu-id="03c84-108">Распространенной причиной этой ошибки является использование класса `Catch e As Exception` внутри обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="03c84-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="03c84-109">Если это так, имя `Catch` переменная блока `ex` вместо `e`.</span><span class="sxs-lookup"><span data-stu-id="03c84-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
-   <span data-ttu-id="03c84-110">Другой распространенной причиной этой ошибки может быть попытка доступа к локальной переменной, объявленной в `Try` блок в отдельном `Catch` блока.</span><span class="sxs-lookup"><span data-stu-id="03c84-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="03c84-111">Чтобы исправить эту ошибку, объявите переменную за пределами `Try...Catch...Finally` структуры.</span><span class="sxs-lookup"><span data-stu-id="03c84-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03c84-112">См. также</span><span class="sxs-lookup"><span data-stu-id="03c84-112">See Also</span></span>  
 [<span data-ttu-id="03c84-113">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="03c84-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="03c84-114">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="03c84-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
