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
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="bf85d-102">Переменные структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf85d-102">Structure Variables (Visual Basic)</span></span>

<span data-ttu-id="bf85d-103">После создания структуры можно объявить переменные уровня процедуры и модуля в качестве этого типа.</span><span class="sxs-lookup"><span data-stu-id="bf85d-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="bf85d-104">Например, можно создать структуру, которая записывает сведения о компьютерной системе.</span><span class="sxs-lookup"><span data-stu-id="bf85d-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="bf85d-105">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="bf85d-105">The following example demonstrates this.</span></span>

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

<span data-ttu-id="bf85d-106">Теперь можно объявлять переменные этого типа.</span><span class="sxs-lookup"><span data-stu-id="bf85d-106">You can now declare variables of that type.</span></span> <span data-ttu-id="bf85d-107">Это показано в следующем объявлении.</span><span class="sxs-lookup"><span data-stu-id="bf85d-107">The following declaration illustrates this.</span></span>

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> <span data-ttu-id="bf85d-108">В классах и модулях структуры, объявленные с помощью [инструкции Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) , по умолчанию имеют открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="bf85d-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="bf85d-109">Если структура должна быть закрытой, убедитесь, что она объявлена с помощью ключевого слова [Private](../../../../visual-basic/language-reference/modifiers/private.md) .</span><span class="sxs-lookup"><span data-stu-id="bf85d-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>

## <a name="access-to-structure-values"></a><span data-ttu-id="bf85d-110">Доступ к значениям структуры</span><span class="sxs-lookup"><span data-stu-id="bf85d-110">Access to Structure Values</span></span>

<span data-ttu-id="bf85d-111">Для присвоения и извлечения значений из элементов переменной структуры используется тот же синтаксис, что и при использовании для задания и получения свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="bf85d-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="bf85d-112">Оператор доступа к членам (`.`) размещается между именем переменной структуры и именем элемента.</span><span class="sxs-lookup"><span data-stu-id="bf85d-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="bf85d-113">В следующем примере осуществляется доступ к элементам переменных, ранее объявленных как тип `systemInfo`.</span><span class="sxs-lookup"><span data-stu-id="bf85d-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a><span data-ttu-id="bf85d-114">Присваивание переменных структуры</span><span class="sxs-lookup"><span data-stu-id="bf85d-114">Assigning Structure Variables</span></span>

<span data-ttu-id="bf85d-115">Можно также присвоить одну переменную другой, если оба имеют один и тот же тип структуры.</span><span class="sxs-lookup"><span data-stu-id="bf85d-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="bf85d-116">Все элементы одной структуры копируются в соответствующие элементы в другом.</span><span class="sxs-lookup"><span data-stu-id="bf85d-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="bf85d-117">Это показано в следующем объявлении.</span><span class="sxs-lookup"><span data-stu-id="bf85d-117">The following declaration illustrates this.</span></span>

```vb
yourSystem = mySystem
```

<span data-ttu-id="bf85d-118">Если элемент структуры является ссылочным типом, например `String`, `Object`или массивом, то копируется указатель на данные.</span><span class="sxs-lookup"><span data-stu-id="bf85d-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="bf85d-119">В предыдущем примере, если `systemInfo` включала объектная переменная, то в предыдущем примере был скопирован указатель из `mySystem` в `yourSystem`, а изменение данных объекта через одну структуру вступит в действие при доступе через другую структуру.</span><span class="sxs-lookup"><span data-stu-id="bf85d-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf85d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="bf85d-120">See also</span></span>

- [<span data-ttu-id="bf85d-121">Типы данных</span><span class="sxs-lookup"><span data-stu-id="bf85d-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="bf85d-122">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="bf85d-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="bf85d-123">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="bf85d-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="bf85d-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="bf85d-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="bf85d-125">Структуры</span><span class="sxs-lookup"><span data-stu-id="bf85d-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="bf85d-126">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="bf85d-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="bf85d-127">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="bf85d-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="bf85d-128">Структуры и другие элементы программирования</span><span class="sxs-lookup"><span data-stu-id="bf85d-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="bf85d-129">Структуры и классы</span><span class="sxs-lookup"><span data-stu-id="bf85d-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="bf85d-130">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="bf85d-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
