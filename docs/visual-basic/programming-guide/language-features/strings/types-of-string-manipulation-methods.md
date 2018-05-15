---
title: Типы методов для работы со строками в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 11903e067c064f129ecd2df80244edb6741c73be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="08dad-102">Типы методов для работы со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="08dad-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="08dad-103">Существует несколько способов для анализа и работы со строками.</span><span class="sxs-lookup"><span data-stu-id="08dad-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="08dad-104">Некоторые методы являются частью языка Visual Basic, а другие принадлежат `String` класса.</span><span class="sxs-lookup"><span data-stu-id="08dad-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="08dad-105">Язык Visual Basic и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="08dad-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="08dad-106">Методы Visual Basic используются как встроенные функции языка.</span><span class="sxs-lookup"><span data-stu-id="08dad-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="08dad-107">Они могут использоваться без уточнения в коде.</span><span class="sxs-lookup"><span data-stu-id="08dad-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="08dad-108">В следующем примере показано типичное использование команды управления строками Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="08dad-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 <span data-ttu-id="08dad-109">В этом примере `Mid` функция выполняет операцию прямой на `aString` и присваивает это значение `bString`.</span><span class="sxs-lookup"><span data-stu-id="08dad-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="08dad-110">Список методов Visual Basic для обработки см. в разделе [Сводка управления строками](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="08dad-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="08dad-111">Общие методы и методы экземпляра</span><span class="sxs-lookup"><span data-stu-id="08dad-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="08dad-112">Строки также можно работать с методами `String` класса.</span><span class="sxs-lookup"><span data-stu-id="08dad-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="08dad-113">Существует два типа методов в `String`: *общего* методы и *экземпляр* методы.</span><span class="sxs-lookup"><span data-stu-id="08dad-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="08dad-114">Общие методы</span><span class="sxs-lookup"><span data-stu-id="08dad-114">Shared Methods</span></span>  
 <span data-ttu-id="08dad-115">Общий метод является методом, основанная на `String` сам класс и не требует экземпляр этого класса для работы.</span><span class="sxs-lookup"><span data-stu-id="08dad-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="08dad-116">Эти методы могут быть дополнены имя класса (`String`), а не с помощью экземпляра `String` класса.</span><span class="sxs-lookup"><span data-stu-id="08dad-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="08dad-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="08dad-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 <span data-ttu-id="08dad-118">В приведенном выше примере <xref:System.String.Copy%2A?displayProperty=nameWithType> метод является статическим методом, который функционирует после выражения он получает и присваивает результирующее значение `bString`.</span><span class="sxs-lookup"><span data-stu-id="08dad-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="08dad-119">Методы экземпляра</span><span class="sxs-lookup"><span data-stu-id="08dad-119">Instance Methods</span></span>  
 <span data-ttu-id="08dad-120">Методы экземпляра, в отличие от этого, возникающих из-за определенный экземпляр `String` и должны быть дополнены именем экземпляра.</span><span class="sxs-lookup"><span data-stu-id="08dad-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="08dad-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="08dad-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 <span data-ttu-id="08dad-122">В этом примере <xref:System.String.Substring%2A?displayProperty=nameWithType> метод является методом экземпляра `String` (то есть, `aString`).</span><span class="sxs-lookup"><span data-stu-id="08dad-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="08dad-123">Он выполняет операцию над `aString` и присваивает это значение `bString`.</span><span class="sxs-lookup"><span data-stu-id="08dad-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="08dad-124">Дополнительные сведения см. в документации для <xref:System.String> класса.</span><span class="sxs-lookup"><span data-stu-id="08dad-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08dad-125">См. также</span><span class="sxs-lookup"><span data-stu-id="08dad-125">See Also</span></span>  
 [<span data-ttu-id="08dad-126">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="08dad-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
