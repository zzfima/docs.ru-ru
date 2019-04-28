---
title: Практическое руководство. Хранение нескольких значений в переменной (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: e2e1648ea508ecdd744adb8d2a4f7fdbc1e586c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906494"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="783e1-102">Практическое руководство. Хранение нескольких значений в переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="783e1-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>
<span data-ttu-id="783e1-103">Переменная содержит более одного значения, если при ее объявлении необходимо иметь *составной тип данных*.</span><span class="sxs-lookup"><span data-stu-id="783e1-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>  
  
 <span data-ttu-id="783e1-104">[Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) содержать структуры, массивы и классы.</span><span class="sxs-lookup"><span data-stu-id="783e1-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="783e1-105">Переменная составные типы данных могут содержать как простые типы данных и других составных типов.</span><span class="sxs-lookup"><span data-stu-id="783e1-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="783e1-106">Классы и структуры могут содержать код, а также данные.</span><span class="sxs-lookup"><span data-stu-id="783e1-106">Structures and classes can hold code as well as data.</span></span>  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="783e1-107">Для хранения более одного значения в переменной</span><span class="sxs-lookup"><span data-stu-id="783e1-107">To hold more than one value in a variable</span></span>  
  
1. <span data-ttu-id="783e1-108">Определите, какой тип составных данных, которые вы хотите использовать для переменной.</span><span class="sxs-lookup"><span data-stu-id="783e1-108">Determine what composite data type you want to use for your variable.</span></span>  
  
2. <span data-ttu-id="783e1-109">Если составной тип данных еще не определен, определите таким образом, чтобы его можно было использовать переменную.</span><span class="sxs-lookup"><span data-stu-id="783e1-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>  
  
    - <span data-ttu-id="783e1-110">Определить структуру с [оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="783e1-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
    - <span data-ttu-id="783e1-111">Определить массив с [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="783e1-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
    - <span data-ttu-id="783e1-112">Определение класса с [оператор Class](../../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="783e1-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
3. <span data-ttu-id="783e1-113">Объявите переменную с `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="783e1-113">Declare your variable with a `Dim` statement.</span></span>  
  
4. <span data-ttu-id="783e1-114">После имени переменной `As` предложение.</span><span class="sxs-lookup"><span data-stu-id="783e1-114">Follow the variable name with an `As` clause.</span></span>  
  
5. <span data-ttu-id="783e1-115">Выполните `As` ключевое слово с именем соответствующего составного типа.</span><span class="sxs-lookup"><span data-stu-id="783e1-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="783e1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="783e1-116">See also</span></span>

- [<span data-ttu-id="783e1-117">Типы данных</span><span class="sxs-lookup"><span data-stu-id="783e1-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="783e1-118">Знаки типов</span><span class="sxs-lookup"><span data-stu-id="783e1-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="783e1-119">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="783e1-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="783e1-120">Структуры</span><span class="sxs-lookup"><span data-stu-id="783e1-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="783e1-121">Массивы</span><span class="sxs-lookup"><span data-stu-id="783e1-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="783e1-122">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="783e1-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="783e1-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="783e1-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
