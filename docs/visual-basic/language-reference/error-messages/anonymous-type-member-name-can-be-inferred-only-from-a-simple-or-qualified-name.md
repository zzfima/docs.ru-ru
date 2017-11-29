---
title: "Имя члена анонимного типа может быть определено только из простого или уточненного имени без аргументов"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords: BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7068928a17ee5fdb7bf6b5e0a40aaa7e5ef32f11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="a52ec-102">Имя члена анонимного типа может быть определено только из простого или уточненного имени без аргументов</span><span class="sxs-lookup"><span data-stu-id="a52ec-102">Anonymous type member name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="a52ec-103">Нельзя вывести имя члена анонимного типа из сложного выражения.</span><span class="sxs-lookup"><span data-stu-id="a52ec-103">You cannot infer an anonymous type member name from a complex expression.</span></span>  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 <span data-ttu-id="a52ec-104">Дополнительные сведения об источниках, из которых можно или нельзя вывести имена и типы членов см. в разделе [как: определить имена свойств и типов в объявлениях анонимных типов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span><span class="sxs-lookup"><span data-stu-id="a52ec-104">For more information about sources from which anonymous types can and cannot infer member names and types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
 <span data-ttu-id="a52ec-105">**Идентификатор ошибки:** BC36556</span><span class="sxs-lookup"><span data-stu-id="a52ec-105">**Error ID:** BC36556</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a52ec-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a52ec-106">To correct this error</span></span>  
  
-   <span data-ttu-id="a52ec-107">Назначьте выражение с именем члена, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="a52ec-107">Assign the expression to a member name, as shown in the following code:</span></span>  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a52ec-108">См. также</span><span class="sxs-lookup"><span data-stu-id="a52ec-108">See Also</span></span>  
 [<span data-ttu-id="a52ec-109">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="a52ec-109">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="a52ec-110">Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов</span><span class="sxs-lookup"><span data-stu-id="a52ec-110">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
