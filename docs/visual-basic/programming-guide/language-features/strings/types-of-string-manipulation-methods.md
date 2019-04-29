---
title: Типы методов для работы со строками в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 44eb101ebdfeb316958a659107190ef1fc84df44
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938272"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="8f505-102">Типы методов для работы со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8f505-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="8f505-103">Существует несколько различных способов анализа и работы со строками.</span><span class="sxs-lookup"><span data-stu-id="8f505-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="8f505-104">Некоторые методы являются частью языка Visual Basic, а другие принадлежат `String` класса.</span><span class="sxs-lookup"><span data-stu-id="8f505-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="8f505-105">Язык Visual Basic и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8f505-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="8f505-106">Методы Visual Basic используются как встроенные функции языка.</span><span class="sxs-lookup"><span data-stu-id="8f505-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="8f505-107">Они могут использоваться без уточнения в коде.</span><span class="sxs-lookup"><span data-stu-id="8f505-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="8f505-108">В следующем примере показано типичное использование команды строками Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="8f505-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="8f505-109">В этом примере `Mid` функция выполняет прямой операцию на `aString` и присваивает это значение `bString`.</span><span class="sxs-lookup"><span data-stu-id="8f505-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="8f505-110">Список методов обработки строк в Visual Basic, см. в разделе [Сводка управления строками](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="8f505-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="8f505-111">Общие методы и методы экземпляра</span><span class="sxs-lookup"><span data-stu-id="8f505-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="8f505-112">Строки также можно работать с методами `String` класса.</span><span class="sxs-lookup"><span data-stu-id="8f505-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="8f505-113">Существует два типа методов в `String`: *общего* методы и *экземпляр* методы.</span><span class="sxs-lookup"><span data-stu-id="8f505-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="8f505-114">Общие методы</span><span class="sxs-lookup"><span data-stu-id="8f505-114">Shared Methods</span></span>  
 <span data-ttu-id="8f505-115">Общий метод является методом, порождаемой `String` сам по себе класс и не требует запуска экземпляра этого класса для работы.</span><span class="sxs-lookup"><span data-stu-id="8f505-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="8f505-116">Эти методы могут быть уточнено именем класса (`String`), а не с экземпляром `String` класса.</span><span class="sxs-lookup"><span data-stu-id="8f505-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="8f505-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="8f505-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="8f505-118">В приведенном выше примере <xref:System.String.Copy%2A?displayProperty=nameWithType> метод — это статический метод, который действует при выражение он предоставляется и присваивает результирующее значение `bString`.</span><span class="sxs-lookup"><span data-stu-id="8f505-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="8f505-119">Методы экземпляра</span><span class="sxs-lookup"><span data-stu-id="8f505-119">Instance Methods</span></span>  
 <span data-ttu-id="8f505-120">Методы экземпляра, напротив, возникающих из-за конкретный экземпляр `String` и должны быть дополнены именем экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8f505-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="8f505-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="8f505-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="8f505-122">В этом примере <xref:System.String.Substring%2A?displayProperty=nameWithType> метод является методом экземпляра `String` (то есть `aString`).</span><span class="sxs-lookup"><span data-stu-id="8f505-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="8f505-123">Он выполняет операцию над `aString` и присваивает это значение `bString`.</span><span class="sxs-lookup"><span data-stu-id="8f505-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="8f505-124">Дополнительные сведения см. в документации по <xref:System.String> класса.</span><span class="sxs-lookup"><span data-stu-id="8f505-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f505-125">См. также</span><span class="sxs-lookup"><span data-stu-id="8f505-125">See also</span></span>

- [<span data-ttu-id="8f505-126">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8f505-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
