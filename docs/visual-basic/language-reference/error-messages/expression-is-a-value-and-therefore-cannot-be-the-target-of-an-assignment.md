---
title: Нельзя присвоить значение выражению, поскольку оно является значением
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: d5aae4d30abbf9ed2af260412352a5e0452e0dcc
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513040"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="464bd-102">Нельзя присвоить значение выражению, поскольку оно является значением</span><span class="sxs-lookup"><span data-stu-id="464bd-102">Expression is a value and therefore cannot be the target of an assignment</span></span>

<span data-ttu-id="464bd-103">Оператор пытается присвоить значение выражению.</span><span class="sxs-lookup"><span data-stu-id="464bd-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="464bd-104">Значение можно назначить только переменной с возможностью записи, свойству или элементу массива во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="464bd-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="464bd-105">В следующем примере показано, как может произойти эта ошибка.</span><span class="sxs-lookup"><span data-stu-id="464bd-105">The following example illustrates how this error can occur.</span></span>

```vb
Dim yesterday As Integer
ReadOnly maximum As Integer = 45
yesterday + 1 = DatePart(DateInterval.Day, Now)
' The preceding line is an ERROR because of an expression on the left.
maximum = 50
' The preceding line is an ERROR because maximum is declared ReadOnly.
```

<span data-ttu-id="464bd-106">Аналогичные примеры могут применяться к свойствам и элементам массива.</span><span class="sxs-lookup"><span data-stu-id="464bd-106">Similar examples could apply to properties and array elements.</span></span>

<span data-ttu-id="464bd-107">**Косвенный доступ.**</span><span class="sxs-lookup"><span data-stu-id="464bd-107">**Indirect Access.**</span></span> <span data-ttu-id="464bd-108">Непрямой доступ через тип значения может также вызвать эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="464bd-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="464bd-109">Рассмотрим следующий пример кода, который пытается задать значение <xref:System.Drawing.Point> путем прямого доступа к нему через. <xref:System.Windows.Forms.Control.Location%2A></span><span class="sxs-lookup"><span data-stu-id="464bd-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>

```vb
' Assume this code runs inside Form1.
Dim exitButton As New System.Windows.Forms.Button()
exitButton.Text = "Exit this form"
exitButton.Location.X = 140
' The preceding line is an ERROR because of no storage for Location.
```

<span data-ttu-id="464bd-110">Последняя инструкция из предыдущего примера завершается сбоем, так как создает только временное выделение для <xref:System.Drawing.Point> структуры, возвращаемой <xref:System.Windows.Forms.Control.Location%2A> свойством.</span><span class="sxs-lookup"><span data-stu-id="464bd-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="464bd-111">Структура является типом значения, а временная структура не сохраняется после выполнения инструкции.</span><span class="sxs-lookup"><span data-stu-id="464bd-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="464bd-112">Проблема решается путем объявления и использования переменной для <xref:System.Windows.Forms.Control.Location%2A>, которая создает более постоянное выделение <xref:System.Drawing.Point> для структуры.</span><span class="sxs-lookup"><span data-stu-id="464bd-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="464bd-113">В следующем примере показан код, который может заменить последнюю инструкцию из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="464bd-113">The following example shows code that can replace the last statement of the preceding example.</span></span>

```vb
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)
exitButton.Location = exitLocation
```

<span data-ttu-id="464bd-114">**Идентификатор ошибки:** BC30068</span><span class="sxs-lookup"><span data-stu-id="464bd-114">**Error ID:** BC30068</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="464bd-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="464bd-115">To correct this error</span></span>

- <span data-ttu-id="464bd-116">Если оператор присваивает значение выражению, замените выражение одной записываемой переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="464bd-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>

- <span data-ttu-id="464bd-117">Если инструкция делает косвенный доступ через тип значения (обычно это структура), создайте переменную для хранения типа значения.</span><span class="sxs-lookup"><span data-stu-id="464bd-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>

- <span data-ttu-id="464bd-118">Назначьте переменной соответствующую структуру (или другой тип значения).</span><span class="sxs-lookup"><span data-stu-id="464bd-118">Assign the appropriate structure (or other value type) to the variable.</span></span>

- <span data-ttu-id="464bd-119">Используйте переменную для доступа к свойству, чтобы присвоить ему значение.</span><span class="sxs-lookup"><span data-stu-id="464bd-119">Use the variable to access the property to assign it a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="464bd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="464bd-120">See also</span></span>

- [<span data-ttu-id="464bd-121">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="464bd-121">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="464bd-122">Операторы</span><span class="sxs-lookup"><span data-stu-id="464bd-122">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="464bd-123">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="464bd-123">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
