---
title: Переменные структуры
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 16b6cdc5a849b50f6caa8b7963dac5c12d63cf3e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346294"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="f6035-102">Переменные структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6035-102">Structure Variables (Visual Basic)</span></span>

<span data-ttu-id="f6035-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span><span class="sxs-lookup"><span data-stu-id="f6035-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="f6035-104">For example, you can create a structure that records information about a computer system.</span><span class="sxs-lookup"><span data-stu-id="f6035-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="f6035-105">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="f6035-105">The following example demonstrates this.</span></span>

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

<span data-ttu-id="f6035-106">You can now declare variables of that type.</span><span class="sxs-lookup"><span data-stu-id="f6035-106">You can now declare variables of that type.</span></span> <span data-ttu-id="f6035-107">The following declaration illustrates this.</span><span class="sxs-lookup"><span data-stu-id="f6035-107">The following declaration illustrates this.</span></span>

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> <span data-ttu-id="f6035-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span><span class="sxs-lookup"><span data-stu-id="f6035-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="f6035-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span><span class="sxs-lookup"><span data-stu-id="f6035-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>

## <a name="access-to-structure-values"></a><span data-ttu-id="f6035-110">Access to Structure Values</span><span class="sxs-lookup"><span data-stu-id="f6035-110">Access to Structure Values</span></span>

<span data-ttu-id="f6035-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span><span class="sxs-lookup"><span data-stu-id="f6035-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="f6035-112">You place the member access operator (`.`) between the structure variable name and the element name.</span><span class="sxs-lookup"><span data-stu-id="f6035-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="f6035-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span><span class="sxs-lookup"><span data-stu-id="f6035-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a><span data-ttu-id="f6035-114">Assigning Structure Variables</span><span class="sxs-lookup"><span data-stu-id="f6035-114">Assigning Structure Variables</span></span>

<span data-ttu-id="f6035-115">You can also assign one variable to another if both are of the same structure type.</span><span class="sxs-lookup"><span data-stu-id="f6035-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="f6035-116">This copies all the elements of one structure to the corresponding elements in the other.</span><span class="sxs-lookup"><span data-stu-id="f6035-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="f6035-117">The following declaration illustrates this.</span><span class="sxs-lookup"><span data-stu-id="f6035-117">The following declaration illustrates this.</span></span>

```vb
yourSystem = mySystem
```

<span data-ttu-id="f6035-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span><span class="sxs-lookup"><span data-stu-id="f6035-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="f6035-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span><span class="sxs-lookup"><span data-stu-id="f6035-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6035-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f6035-120">See also</span></span>

- [<span data-ttu-id="f6035-121">Типы данных</span><span class="sxs-lookup"><span data-stu-id="f6035-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="f6035-122">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="f6035-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="f6035-123">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="f6035-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="f6035-124">Типы значений и ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="f6035-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="f6035-125">Структуры</span><span class="sxs-lookup"><span data-stu-id="f6035-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="f6035-126">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="f6035-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="f6035-127">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="f6035-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="f6035-128">Структуры и другие элементы программирования</span><span class="sxs-lookup"><span data-stu-id="f6035-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="f6035-129">Структуры и классы</span><span class="sxs-lookup"><span data-stu-id="f6035-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="f6035-130">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="f6035-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
