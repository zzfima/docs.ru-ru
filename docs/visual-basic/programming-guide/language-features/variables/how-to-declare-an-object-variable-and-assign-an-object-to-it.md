---
title: Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 1f38c90f0571b3fc73c4c89812092cdada936d84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="11d8c-102">Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта</span><span class="sxs-lookup"><span data-stu-id="11d8c-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>
<span data-ttu-id="11d8c-103">Объявите переменную [тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) , указав `As Object` в [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="11d8c-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="11d8c-104">Чтобы присвоить объект такой переменной, поместите его после знака равенства (`=`) в предложении назначения инструкции или инициализации.</span><span class="sxs-lookup"><span data-stu-id="11d8c-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11d8c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="11d8c-105">Example</span></span>  
 <span data-ttu-id="11d8c-106">В следующем примере объявляется `Object` переменной и назначает текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="11d8c-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 <span data-ttu-id="11d8c-107">Объявление и присваивания можно объединять путем инициализации переменной в рамках его объявления.</span><span class="sxs-lookup"><span data-stu-id="11d8c-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="11d8c-108">Следующий пример соответствует предыдущему примеру.</span><span class="sxs-lookup"><span data-stu-id="11d8c-108">The following example is equivalent to the preceding example.</span></span>  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="11d8c-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="11d8c-109">Compiling the Code</span></span>  
 <span data-ttu-id="11d8c-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="11d8c-110">This example requires:</span></span>  
  
-   <span data-ttu-id="11d8c-111">ссылка на пространство имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="11d8c-111">A reference to the <xref:System> namespace.</span></span>  
  
-   <span data-ttu-id="11d8c-112">Класс, структура или модуль, в котором для размещения `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="11d8c-112">A class, structure, or module in which to put the `Dim` statement.</span></span>  
  
-   <span data-ttu-id="11d8c-113">Процедура, в которую будет помещен оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="11d8c-113">A procedure in which to put the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d8c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="11d8c-114">See Also</span></span>  
 [<span data-ttu-id="11d8c-115">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="11d8c-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="11d8c-116">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="11d8c-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="11d8c-117">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="11d8c-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="11d8c-118">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="11d8c-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="11d8c-119">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="11d8c-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="11d8c-120">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="11d8c-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="11d8c-121">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="11d8c-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
