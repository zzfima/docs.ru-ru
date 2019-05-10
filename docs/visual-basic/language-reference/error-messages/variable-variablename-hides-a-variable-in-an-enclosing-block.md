---
title: Переменная <variablename> скрывает содержащуюся в блоке переменную
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 36fe543dd4546c6fe930f259a55cea856917370f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662668"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="9b520-102">Переменная "\<имя_переменной >" скрывает переменную во внешнем блоке</span><span class="sxs-lookup"><span data-stu-id="9b520-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="9b520-103">Содержится в блоке, переменная имеет имя, совпадающее с именем другой локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="9b520-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="9b520-104">**Идентификатор ошибки:** BC30616</span><span class="sxs-lookup"><span data-stu-id="9b520-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9b520-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9b520-105">To correct this error</span></span>  
  
- <span data-ttu-id="9b520-106">Переименуйте переменную в закрытом блоке, так как это не так же, как локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="9b520-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="9b520-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="9b520-107">For example:</span></span>  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- <span data-ttu-id="9b520-108">Распространенной причиной этой ошибки является использование `Catch e As Exception` внутри обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="9b520-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="9b520-109">Если это так, имя `Catch` переменная блока `ex` вместо `e`.</span><span class="sxs-lookup"><span data-stu-id="9b520-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
- <span data-ttu-id="9b520-110">Другой распространенной причиной этой ошибки является попытка получить доступ к локальной переменной, объявленной в `Try` блокировать в отдельном `Catch` блока.</span><span class="sxs-lookup"><span data-stu-id="9b520-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="9b520-111">Чтобы исправить эту ошибку, объявите переменную за пределами `Try...Catch...Finally` структуры.</span><span class="sxs-lookup"><span data-stu-id="9b520-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b520-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9b520-112">See also</span></span>

- [<span data-ttu-id="9b520-113">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="9b520-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="9b520-114">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="9b520-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
