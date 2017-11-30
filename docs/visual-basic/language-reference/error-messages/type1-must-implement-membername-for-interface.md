---
title: "&lt;Тип 1&gt;&#39;&lt; TypeName&gt;&#39; необходимо реализовать &#39;&lt; имя пользователя&gt;&#39; для интерфейса &#39;&lt; Имя интерфейса&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords: BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05e0229d0259c519d4db265c017a5040b425c79a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="98c62-102">&lt;Тип 1&gt;&#39;&lt; TypeName&gt;&#39; необходимо реализовать &#39;&lt; имя пользователя&gt;&#39; для интерфейса &#39;&lt; Имя интерфейса&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="98c62-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;membername&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="98c62-103">"\<typename >" должен реализовывать "\<имя_члена >" для интерфейса "\<имя_интерфейса >".</span><span class="sxs-lookup"><span data-stu-id="98c62-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="98c62-104">Свойство реализации должно иметь соответствующие «ReadOnly» или «WriteOnly» спецификаторы.</span><span class="sxs-lookup"><span data-stu-id="98c62-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="98c62-105">Класс или структура объявляет о реализации интерфейса, но не реализует процедуру, свойство или событие, определенные интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="98c62-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="98c62-106">Каждый член интерфейса должен быть реализован.</span><span class="sxs-lookup"><span data-stu-id="98c62-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="98c62-107">**Идентификатор ошибки:** BC30154</span><span class="sxs-lookup"><span data-stu-id="98c62-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="98c62-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="98c62-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="98c62-109">Объявите член с тем же именем и сигнатурой, что определенный в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="98c62-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="98c62-110">Не забудьте добавить по крайней мере `End Function`, `End Sub`, или `End Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="98c62-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="98c62-111">Добавить `Implements` предложение в конец `Function`, `Sub`, `Property`, или `Event` инструкции.</span><span class="sxs-lookup"><span data-stu-id="98c62-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="98c62-112">Например:</span><span class="sxs-lookup"><span data-stu-id="98c62-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  <span data-ttu-id="98c62-113">При реализации свойства, убедитесь, что `ReadOnly` или `WriteOnly` используется таким же образом, как и в определении интерфейса.</span><span class="sxs-lookup"><span data-stu-id="98c62-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4.  <span data-ttu-id="98c62-114">При реализации свойства объявить `Get` и `Set` соответствующим процедурам.</span><span class="sxs-lookup"><span data-stu-id="98c62-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98c62-115">См. также</span><span class="sxs-lookup"><span data-stu-id="98c62-115">See Also</span></span>  
 [<span data-ttu-id="98c62-116">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="98c62-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="98c62-117">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="98c62-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
