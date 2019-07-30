---
title: Переменные структуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: a86a60def9ac1b8140194ecb6f5e784c62a0e101
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630966"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="a8003-102">Переменные структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8003-102">Structure Variables (Visual Basic)</span></span>

<span data-ttu-id="a8003-103">После создания структуры можно объявить переменные уровня процедуры и модуля в качестве этого типа.</span><span class="sxs-lookup"><span data-stu-id="a8003-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="a8003-104">Например, можно создать структуру, которая записывает сведения о компьютерной системе.</span><span class="sxs-lookup"><span data-stu-id="a8003-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="a8003-105">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="a8003-105">The following example demonstrates this.</span></span>

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

<span data-ttu-id="a8003-106">Теперь можно объявлять переменные этого типа.</span><span class="sxs-lookup"><span data-stu-id="a8003-106">You can now declare variables of that type.</span></span> <span data-ttu-id="a8003-107">Это показано в следующем объявлении.</span><span class="sxs-lookup"><span data-stu-id="a8003-107">The following declaration illustrates this.</span></span>

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> <span data-ttu-id="a8003-108">В классах и модулях структуры, объявленные с помощью [инструкции Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) , по умолчанию имеют открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="a8003-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="a8003-109">Если структура должна быть закрытой, убедитесь, что она объявлена с помощью ключевого слова [Private](../../../../visual-basic/language-reference/modifiers/private.md) .</span><span class="sxs-lookup"><span data-stu-id="a8003-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>

## <a name="access-to-structure-values"></a><span data-ttu-id="a8003-110">Доступ к значениям структуры</span><span class="sxs-lookup"><span data-stu-id="a8003-110">Access to Structure Values</span></span>

<span data-ttu-id="a8003-111">Для присвоения и извлечения значений из элементов переменной структуры используется тот же синтаксис, что и при использовании для задания и получения свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="a8003-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="a8003-112">Оператор доступа к членам (`.`) размещается между именем переменной структуры и именем элемента.</span><span class="sxs-lookup"><span data-stu-id="a8003-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="a8003-113">В следующем примере осуществляется доступ к элементам переменных, ранее объявленных как `systemInfo`тип.</span><span class="sxs-lookup"><span data-stu-id="a8003-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a><span data-ttu-id="a8003-114">Присваивание переменных структуры</span><span class="sxs-lookup"><span data-stu-id="a8003-114">Assigning Structure Variables</span></span>

<span data-ttu-id="a8003-115">Можно также присвоить одну переменную другой, если оба имеют один и тот же тип структуры.</span><span class="sxs-lookup"><span data-stu-id="a8003-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="a8003-116">Все элементы одной структуры копируются в соответствующие элементы в другом.</span><span class="sxs-lookup"><span data-stu-id="a8003-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="a8003-117">Это показано в следующем объявлении.</span><span class="sxs-lookup"><span data-stu-id="a8003-117">The following declaration illustrates this.</span></span>

```vb
yourSystem = mySystem
```

<span data-ttu-id="a8003-118">Если элемент структуры является ссылочным типом, таким как `String` `Object`массив типа, или, то копируется указатель на данные.</span><span class="sxs-lookup"><span data-stu-id="a8003-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="a8003-119">В предыдущем примере, если `systemInfo` был добавлен объектная переменная, в предыдущем примере был скопирован указатель из `mySystem` в `yourSystem`, а изменение данных объекта через одну структуру вступит в действие при обращении к через другую структуру.</span><span class="sxs-lookup"><span data-stu-id="a8003-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8003-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a8003-120">See also</span></span>

- [<span data-ttu-id="a8003-121">Типы данных</span><span class="sxs-lookup"><span data-stu-id="a8003-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="a8003-122">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="a8003-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="a8003-123">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="a8003-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="a8003-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="a8003-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="a8003-125">Структуры</span><span class="sxs-lookup"><span data-stu-id="a8003-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a8003-126">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="a8003-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="a8003-127">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="a8003-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="a8003-128">Структуры и другие элементы программирования</span><span class="sxs-lookup"><span data-stu-id="a8003-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="a8003-129">Структуры и классы</span><span class="sxs-lookup"><span data-stu-id="a8003-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="a8003-130">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="a8003-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
