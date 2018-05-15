---
title: Нельзя присвоить значение выражению, поскольку оно является значением
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: dd5618bd0533f885a6aef8229b2d8cb1bc34c237
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="fde1f-102">Нельзя присвоить значение выражению, поскольку оно является значением</span><span class="sxs-lookup"><span data-stu-id="fde1f-102">Expression is a value and therefore cannot be the target of an assignment</span></span>
<span data-ttu-id="fde1f-103">Оператор пытается присвоить значение выражению.</span><span class="sxs-lookup"><span data-stu-id="fde1f-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="fde1f-104">Можно назначить значение только записываемой переменной, свойства или элемента массива во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fde1f-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="fde1f-105">В следующем примере показано, как эта ошибка может возникать.</span><span class="sxs-lookup"><span data-stu-id="fde1f-105">The following example illustrates how this error can occur.</span></span>  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 <span data-ttu-id="fde1f-106">Аналогичные примеры можно применить к свойствам и элементам массива.</span><span class="sxs-lookup"><span data-stu-id="fde1f-106">Similar examples could apply to properties and array elements.</span></span>  
  
 <span data-ttu-id="fde1f-107">**Косвенный доступ.**</span><span class="sxs-lookup"><span data-stu-id="fde1f-107">**Indirect Access.**</span></span> <span data-ttu-id="fde1f-108">Эту ошибку может также вызывать косвенный доступ через тип значения.</span><span class="sxs-lookup"><span data-stu-id="fde1f-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="fde1f-109">Рассмотрим следующий пример кода, который пытается установить значение <xref:System.Drawing.Point> , обратившись к косвенно через <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="fde1f-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 <span data-ttu-id="fde1f-110">Последней инструкцией в предыдущем примере завершается ошибкой, так как она создает временный выделение для <xref:System.Drawing.Point> структуры, возвращенный <xref:System.Windows.Forms.Control.Location%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="fde1f-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="fde1f-111">Структура является типом значения, а временная структура не сохраняется после выполнения инструкции.</span><span class="sxs-lookup"><span data-stu-id="fde1f-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="fde1f-112">Проблемы путем объявления и использования переменной для <xref:System.Windows.Forms.Control.Location%2A>, которая создает постоянное выделение памяти для <xref:System.Drawing.Point> структуры.</span><span class="sxs-lookup"><span data-stu-id="fde1f-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="fde1f-113">В примере показан код, который можно заменить последней инструкции в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="fde1f-113">The following example shows code that can replace the last statement of the preceding example.</span></span>  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 <span data-ttu-id="fde1f-114">**Идентификатор ошибки:** BC30068</span><span class="sxs-lookup"><span data-stu-id="fde1f-114">**Error ID:** BC30068</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fde1f-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="fde1f-115">To correct this error</span></span>  
  
-   <span data-ttu-id="fde1f-116">Если инструкция присваивает значение выражения, замените выражение одной записываемой переменной, свойства или элемента массива.</span><span class="sxs-lookup"><span data-stu-id="fde1f-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>  
  
-   <span data-ttu-id="fde1f-117">Если инструкция делает косвенный доступ через тип значения (обычно структуры), создайте переменную для хранения типа значения.</span><span class="sxs-lookup"><span data-stu-id="fde1f-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>  
  
-   <span data-ttu-id="fde1f-118">Присвойте переменной подходящую структуру (или другого типа значения).</span><span class="sxs-lookup"><span data-stu-id="fde1f-118">Assign the appropriate structure (or other value type) to the variable.</span></span>  
  
-   <span data-ttu-id="fde1f-119">Используйте переменную для доступа к свойству присвоено значение.</span><span class="sxs-lookup"><span data-stu-id="fde1f-119">Use the variable to access the property to assign it a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde1f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fde1f-120">See Also</span></span>  
 [<span data-ttu-id="fde1f-121">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="fde1f-121">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="fde1f-122">Операторы</span><span class="sxs-lookup"><span data-stu-id="fde1f-122">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="fde1f-123">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="fde1f-123">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
