---
title: Как выполнить Объявление объектной переменной и присвоение объекта в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 86037499b44d17f2ba83fd6cd0dad83ceb14e6b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730091"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="6592b-102">Как выполнить Объявление объектной переменной и присвоение объекта в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6592b-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>
<span data-ttu-id="6592b-103">Объявите переменную [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) , указав `As Object` в [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6592b-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="6592b-104">Чтобы присвоить объект на такую переменную, поместите его после знака равенства (`=`) в предложении назначения инструкции или инициализации.</span><span class="sxs-lookup"><span data-stu-id="6592b-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6592b-105">Пример</span><span class="sxs-lookup"><span data-stu-id="6592b-105">Example</span></span>  
 <span data-ttu-id="6592b-106">В следующем примере объявляется `Object` переменной и назначает текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="6592b-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 <span data-ttu-id="6592b-107">Назначение и объявление можно объединять путем инициализации переменной при ее объявлении.</span><span class="sxs-lookup"><span data-stu-id="6592b-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="6592b-108">Следующий пример является эквивалентом предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="6592b-108">The following example is equivalent to the preceding example.</span></span>  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6592b-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="6592b-109">Compiling the Code</span></span>  
 <span data-ttu-id="6592b-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="6592b-110">This example requires:</span></span>  
  
-   <span data-ttu-id="6592b-111">ссылка на пространство имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="6592b-111">A reference to the <xref:System> namespace.</span></span>  
  
-   <span data-ttu-id="6592b-112">Класс, структура или модуль, в который помещаются `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="6592b-112">A class, structure, or module in which to put the `Dim` statement.</span></span>  
  
-   <span data-ttu-id="6592b-113">Процедура, в который помещаются оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="6592b-113">A procedure in which to put the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6592b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6592b-114">See also</span></span>
- [<span data-ttu-id="6592b-115">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="6592b-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="6592b-116">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="6592b-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="6592b-117">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="6592b-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="6592b-118">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="6592b-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="6592b-119">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="6592b-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="6592b-120">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="6592b-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="6592b-121">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="6592b-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
