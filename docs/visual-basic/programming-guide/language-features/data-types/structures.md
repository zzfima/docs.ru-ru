---
title: Структуры (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic]
- user-defined data types [Visual Basic], structures
- user-defined types [Visual Basic], about user-defined types
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], about user-defined data types
- types [Visual Basic], user-defined
ms.assetid: 55e86462-5e99-4d33-8018-6d097ca491b2
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1f537b25a405548816ab3d356a18f693a5d0006
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="structures-visual-basic"></a><span data-ttu-id="c754a-102">Структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c754a-102">Structures (Visual Basic)</span></span>
<span data-ttu-id="c754a-103">Объект *структура* представляет собой обобщение определяемых пользователем типов (UDT), поддерживается в предыдущих версиях Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c754a-103">A *structure* is a generalization of the user-defined type (UDT) supported by previous versions of Visual Basic.</span></span> <span data-ttu-id="c754a-104">Дополнение к полям структуры могут предоставлять свойства, методы и события.</span><span class="sxs-lookup"><span data-stu-id="c754a-104">In addition to fields, structures can expose properties, methods, and events.</span></span> <span data-ttu-id="c754a-105">Структура может реализовать один или несколько интерфейсов, и можно объявлять индивидуальные уровни доступа для каждого поля.</span><span class="sxs-lookup"><span data-stu-id="c754a-105">A structure can implement one or more interfaces, and you can declare individual access levels for each field.</span></span>  
  
 <span data-ttu-id="c754a-106">Можно комбинировать элементы данных различных типов для создания структуры.</span><span class="sxs-lookup"><span data-stu-id="c754a-106">You can combine data items of different types to create a structure.</span></span> <span data-ttu-id="c754a-107">Структуры связывают один или несколько *элементы* друг с другом и с самой структурой.</span><span class="sxs-lookup"><span data-stu-id="c754a-107">A structure associates one or more *elements* with each other and with the structure itself.</span></span> <span data-ttu-id="c754a-108">При объявлении структуры, он становится *составной тип данных*, и можно объявлять переменные этого типа.</span><span class="sxs-lookup"><span data-stu-id="c754a-108">When you declare a structure, it becomes a *composite data type*, and you can declare variables of that type.</span></span>  
  
 <span data-ttu-id="c754a-109">Структуры полезны в тех случаях, когда требуется одну переменную для хранения связанных части сведений.</span><span class="sxs-lookup"><span data-stu-id="c754a-109">Structures are useful when you want a single variable to hold several related pieces of information.</span></span> <span data-ttu-id="c754a-110">Например может потребоваться сохранить вместе имя, телефон и заработной платы сотрудника.</span><span class="sxs-lookup"><span data-stu-id="c754a-110">For example, you might want to keep an employee's name, telephone extension, and salary together.</span></span> <span data-ttu-id="c754a-111">Эти сведения можно использовать несколько переменных, или можно определить структуру и использовать ее для одной переменной сотрудника.</span><span class="sxs-lookup"><span data-stu-id="c754a-111">You could use several variables for this information, or you could define a structure and use it for a single employee variable.</span></span> <span data-ttu-id="c754a-112">Преимущества структуры становится очевидным, когда имеется много сотрудников и поэтому многие экземпляры переменной.</span><span class="sxs-lookup"><span data-stu-id="c754a-112">The advantage of the structure becomes apparent when you have many employees and therefore many instances of the variable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c754a-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c754a-113">In This Section</span></span>  
 [<span data-ttu-id="c754a-114">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="c754a-114">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 <span data-ttu-id="c754a-115">Показан способ объявления структуры и его элементов.</span><span class="sxs-lookup"><span data-stu-id="c754a-115">Shows how to declare a structure and its elements.</span></span>  
  
 [<span data-ttu-id="c754a-116">Переменные структуры</span><span class="sxs-lookup"><span data-stu-id="c754a-116">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 <span data-ttu-id="c754a-117">Описание присваивания структуры переменной и доступ к его элементам.</span><span class="sxs-lookup"><span data-stu-id="c754a-117">Covers assigning a structure to a variable and accessing its elements.</span></span>  
  
 [<span data-ttu-id="c754a-118">Структуры и другие элементы программирования</span><span class="sxs-lookup"><span data-stu-id="c754a-118">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 <span data-ttu-id="c754a-119">Описание, способов взаимодействия структур с массивами, объектами, процедуры и друг с другом.</span><span class="sxs-lookup"><span data-stu-id="c754a-119">Summarizes how structures interact with arrays, objects, procedures, and each other.</span></span>  
  
 [<span data-ttu-id="c754a-120">Структуры и классы</span><span class="sxs-lookup"><span data-stu-id="c754a-120">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 <span data-ttu-id="c754a-121">Описывает сходства и различия между структурами и классами.</span><span class="sxs-lookup"><span data-stu-id="c754a-121">Describes the similarities and differences between structures and classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c754a-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c754a-122">Related Sections</span></span>  
 [<span data-ttu-id="c754a-123">Типы данных</span><span class="sxs-lookup"><span data-stu-id="c754a-123">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="c754a-124">Знакомство с типами данных Visual Basic и описывается их использование.</span><span class="sxs-lookup"><span data-stu-id="c754a-124">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="c754a-125">Типы данных</span><span class="sxs-lookup"><span data-stu-id="c754a-125">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="c754a-126">Список простейших типов данных в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c754a-126">Lists the elementary data types supplied by Visual Basic.</span></span>
