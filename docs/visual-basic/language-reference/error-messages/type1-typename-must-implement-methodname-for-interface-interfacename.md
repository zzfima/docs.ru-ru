---
title: <type1>'<typename>«должен реализовывать»<methodname>«для интерфейса»<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c387b0225375f4675042bef593b23a084305b4fd
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591597"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="0cd25-102">\<тип1 > '\<typename >' должен реализовывать '\<имя_метода >' для интерфейса '\<имя_интерфейса >'</span><span class="sxs-lookup"><span data-stu-id="0cd25-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="0cd25-103">Класс или структура требует реализации интерфейса, но не реализует процедуру, определенную интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="0cd25-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="0cd25-104">Каждый член интерфейса должен быть реализован.</span><span class="sxs-lookup"><span data-stu-id="0cd25-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="0cd25-105">**Идентификатор ошибки:** BC30149</span><span class="sxs-lookup"><span data-stu-id="0cd25-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0cd25-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0cd25-106">To correct this error</span></span>  
  
1. <span data-ttu-id="0cd25-107">Объявите процедуру с тем же именем и сигнатурой, как определено в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="0cd25-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="0cd25-108">Обязательно включите по крайней мере `End Function` или `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="0cd25-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="0cd25-109">Добавьте предложение `Implements` в конец оператора `Function` или `Sub`.</span><span class="sxs-lookup"><span data-stu-id="0cd25-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="0cd25-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="0cd25-110">For example:</span></span>  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0cd25-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0cd25-111">See also</span></span>

- [<span data-ttu-id="0cd25-112">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="0cd25-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="0cd25-113">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="0cd25-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
