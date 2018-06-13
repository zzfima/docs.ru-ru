---
title: Переменные структуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 0dad7bdcac5428753e252f3b26ca0a127c293a7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648503"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="b44eb-102">Переменные структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b44eb-102">Structure Variables (Visual Basic)</span></span>
<span data-ttu-id="b44eb-103">После создания структуры можно объявить переменные уровня модуля и процедуры для определенного типа.</span><span class="sxs-lookup"><span data-stu-id="b44eb-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="b44eb-104">Например можно создать структуру, которая записывает сведения о системе компьютера.</span><span class="sxs-lookup"><span data-stu-id="b44eb-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="b44eb-105">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="b44eb-105">The following example demonstrates this.</span></span>  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 <span data-ttu-id="b44eb-106">Можно объявить переменные этого типа.</span><span class="sxs-lookup"><span data-stu-id="b44eb-106">You can now declare variables of that type.</span></span> <span data-ttu-id="b44eb-107">Это показано в следующем объявлении.</span><span class="sxs-lookup"><span data-stu-id="b44eb-107">The following declaration illustrates this.</span></span>  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  <span data-ttu-id="b44eb-108">В классы и модули, структуры объявляются с помощью [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) по умолчанию для общего доступа.</span><span class="sxs-lookup"><span data-stu-id="b44eb-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="b44eb-109">Если структура должна быть закрытой, убедитесь в том, объявите его с помощью [закрытый](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="b44eb-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>  
  
## <a name="access-to-structure-values"></a><span data-ttu-id="b44eb-110">Доступ к значениям структуры</span><span class="sxs-lookup"><span data-stu-id="b44eb-110">Access to Structure Values</span></span>  
 <span data-ttu-id="b44eb-111">Для назначения и извлечения значений из переменных структуры элементов, используйте тот же синтаксис, как используются для задания и получения свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="b44eb-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="b44eb-112">Поместите оператор доступа к членам (`.`) между именем переменной структуры и имя элемента.</span><span class="sxs-lookup"><span data-stu-id="b44eb-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="b44eb-113">Следующий пример получает доступ к элементам переменных, ранее объявленных как тип `systemInfo`.</span><span class="sxs-lookup"><span data-stu-id="b44eb-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a><span data-ttu-id="b44eb-114">Присваивание переменных структуры</span><span class="sxs-lookup"><span data-stu-id="b44eb-114">Assigning Structure Variables</span></span>  
 <span data-ttu-id="b44eb-115">Также можно присвоить одну переменную в другой, если оба имеют одинаковый тип структуры.</span><span class="sxs-lookup"><span data-stu-id="b44eb-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="b44eb-116">Соответствующие элементы в других это копирует все элементы из одной структуры.</span><span class="sxs-lookup"><span data-stu-id="b44eb-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="b44eb-117">Это показано в следующем объявлении.</span><span class="sxs-lookup"><span data-stu-id="b44eb-117">The following declaration illustrates this.</span></span>  
  
```  
yourSystem = mySystem  
```  
  
 <span data-ttu-id="b44eb-118">Если элемент структуры является ссылочным типом, например `String`, `Object`, или копируются в массив, указатель на данные.</span><span class="sxs-lookup"><span data-stu-id="b44eb-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="b44eb-119">В предыдущем примере если `systemInfo` бы были включены переменной объекта, а затем копируется указатель из предыдущего примера `mySystem` для `yourSystem`, и изменение данных объекта через одну структуру будет действовать, если доступ осуществляется через другую структуру.</span><span class="sxs-lookup"><span data-stu-id="b44eb-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b44eb-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b44eb-120">See Also</span></span>  
 [<span data-ttu-id="b44eb-121">Типы данных</span><span class="sxs-lookup"><span data-stu-id="b44eb-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="b44eb-122">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="b44eb-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="b44eb-123">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="b44eb-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="b44eb-124">Типы значений и ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="b44eb-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="b44eb-125">Структуры</span><span class="sxs-lookup"><span data-stu-id="b44eb-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="b44eb-126">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="b44eb-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="b44eb-127">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="b44eb-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="b44eb-128">Структуры и другие элементы программирования</span><span class="sxs-lookup"><span data-stu-id="b44eb-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [<span data-ttu-id="b44eb-129">Структуры и классы</span><span class="sxs-lookup"><span data-stu-id="b44eb-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [<span data-ttu-id="b44eb-130">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="b44eb-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
