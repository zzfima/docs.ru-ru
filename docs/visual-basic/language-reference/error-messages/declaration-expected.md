---
title: Ожидается объявление
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 97bd1701a8a07c39d08a9276cdb929bc9425c1f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="declaration-expected"></a><span data-ttu-id="81450-102">Ожидается объявление</span><span class="sxs-lookup"><span data-stu-id="81450-102">Declaration expected</span></span>
<span data-ttu-id="81450-103">Недекларативный оператор, например оператор присваивания или цикла, находится вне процедуры.</span><span class="sxs-lookup"><span data-stu-id="81450-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="81450-104">Вне процедур могут находиться только объявления.</span><span class="sxs-lookup"><span data-stu-id="81450-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="81450-105">Кроме того, программный элемент объявлен без ключевого слова объявления таких как `Dim` или `Const`.</span><span class="sxs-lookup"><span data-stu-id="81450-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="81450-106">**Идентификатор ошибки:** BC30188</span><span class="sxs-lookup"><span data-stu-id="81450-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="81450-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="81450-107">To correct this error</span></span>  
  
-   <span data-ttu-id="81450-108">Переместите недекларативный оператор в текст процедуры.</span><span class="sxs-lookup"><span data-stu-id="81450-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
-   <span data-ttu-id="81450-109">В начале объявления соответствующее ключевое слово объявления.</span><span class="sxs-lookup"><span data-stu-id="81450-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
-   <span data-ttu-id="81450-110">Убедитесь, что ключевым словом объявления его имя указано верно.</span><span class="sxs-lookup"><span data-stu-id="81450-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81450-111">См. также</span><span class="sxs-lookup"><span data-stu-id="81450-111">See Also</span></span>  
 [<span data-ttu-id="81450-112">Процедуры</span><span class="sxs-lookup"><span data-stu-id="81450-112">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="81450-113">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="81450-113">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
