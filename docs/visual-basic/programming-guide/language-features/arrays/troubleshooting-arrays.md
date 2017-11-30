---
title: "Устранение неполадок, связанных с массивами (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0417ae8d37642a65b14cc81ae9dcf3a3c32d63ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="3f062-102">Устранение неполадок, связанных с массивами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f062-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="3f062-103">Этой странице перечислены некоторые общие проблемы, которые могут возникнуть при работе с массивами.</span><span class="sxs-lookup"><span data-stu-id="3f062-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="3f062-104">Ошибки компиляции, объявления и инициализации массива</span><span class="sxs-lookup"><span data-stu-id="3f062-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="3f062-105">Ошибки компиляции могут возникать из касающаяся правил для объявления, создания и инициализации массивов.</span><span class="sxs-lookup"><span data-stu-id="3f062-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="3f062-106">Ниже перечислены наиболее распространенные причины ошибок:</span><span class="sxs-lookup"><span data-stu-id="3f062-106">The most common causes of errors are the following:</span></span>  
  
-   <span data-ttu-id="3f062-107">Предоставление [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) предложение после указания размерностей при объявлении переменной массива.</span><span class="sxs-lookup"><span data-stu-id="3f062-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="3f062-108">В следующих строках кода показывают недопустимые объявления этого типа.</span><span class="sxs-lookup"><span data-stu-id="3f062-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   <span data-ttu-id="3f062-109">Указание длины по измерениям дольше, чем массива верхнего уровня массива массивов.</span><span class="sxs-lookup"><span data-stu-id="3f062-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="3f062-110">Следующая строка кода показывает недопустимое объявление этого типа.</span><span class="sxs-lookup"><span data-stu-id="3f062-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   <span data-ttu-id="3f062-111">Пропуск `New` ключевое слово, при указании значения элементов.</span><span class="sxs-lookup"><span data-stu-id="3f062-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="3f062-112">Следующая строка кода показывает недопустимое объявление этого типа.</span><span class="sxs-lookup"><span data-stu-id="3f062-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   <span data-ttu-id="3f062-113">Предоставление `New` предложение без фигурных скобок (`{}`).</span><span class="sxs-lookup"><span data-stu-id="3f062-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="3f062-114">В следующих строках кода показывают недопустимые объявления этого типа.</span><span class="sxs-lookup"><span data-stu-id="3f062-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="3f062-115">Доступ к массиву за пределы допустимого диапазона</span><span class="sxs-lookup"><span data-stu-id="3f062-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="3f062-116">Процесс инициализации массива назначает верхнюю и нижнюю границу для каждого измерения.</span><span class="sxs-lookup"><span data-stu-id="3f062-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="3f062-117">У каждого доступа к элементу массива необходимо указать допустимый индекс или индекс для любой размерности.</span><span class="sxs-lookup"><span data-stu-id="3f062-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="3f062-118">Если индекс меньше его нижней границы или выше верхней границы, <xref:System.IndexOutOfRangeException> результаты исключения.</span><span class="sxs-lookup"><span data-stu-id="3f062-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="3f062-119">Компилятор не может обнаружить такую ошибку, поэтому во время выполнения возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="3f062-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="3f062-120">Определение границ</span><span class="sxs-lookup"><span data-stu-id="3f062-120">Determining Bounds</span></span>  
 <span data-ttu-id="3f062-121">Если другой компонент передает массив в коде, например в качестве аргумента процедуры, вы не знаете размер массива или длина его измерений.</span><span class="sxs-lookup"><span data-stu-id="3f062-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="3f062-122">Всегда следует определить верхнюю границу для каждого измерения массива, прежде чем пытаться получить доступ к какие-либо элементы.</span><span class="sxs-lookup"><span data-stu-id="3f062-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="3f062-123">Если массив был создан с помощью некоторых средств отличный от [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `New` предложения, нижняя граница может быть нечто, отличное от 0 и безопаснее определить, что нижняя граница.</span><span class="sxs-lookup"><span data-stu-id="3f062-123">If the array has been created by some means other than a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="3f062-124">Указание измерения</span><span class="sxs-lookup"><span data-stu-id="3f062-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="3f062-125">При определении границ многомерного массива, будьте внимательны, как указать измерения.</span><span class="sxs-lookup"><span data-stu-id="3f062-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="3f062-126">`dimension` Параметры <xref:System.Array.GetLowerBound%2A> и <xref:System.Array.GetUpperBound%2A> методов начинаются с 0, при `Rank` параметры [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A> и <xref:Microsoft.VisualBasic.Information.UBound%2A> функции основаны на 1.</span><span class="sxs-lookup"><span data-stu-id="3f062-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f062-127">См. также</span><span class="sxs-lookup"><span data-stu-id="3f062-127">See Also</span></span>  
 [<span data-ttu-id="3f062-128">Массивы</span><span class="sxs-lookup"><span data-stu-id="3f062-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 <span data-ttu-id="3f062-129">[How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Практическое руководство. Инициализация переменной массива в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f062-129">[How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span></span>
