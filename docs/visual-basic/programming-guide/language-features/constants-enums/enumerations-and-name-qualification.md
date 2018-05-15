---
title: Перечисления и уточнение имен (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: eb1f5653d968e81168833cd57813219e8f049b70
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="enumerations-and-name-qualification-visual-basic"></a><span data-ttu-id="043cd-102">Перечисления и уточнение имен (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="043cd-102">Enumerations and Name Qualification (Visual Basic)</span></span>
<span data-ttu-id="043cd-103">Обычно при ссылке на член перечисления необходимо уточнить имя члена перечисления.</span><span class="sxs-lookup"><span data-stu-id="043cd-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span></span> <span data-ttu-id="043cd-104">Например, для обращения к `Sunday` членом вашей `Days` перечисления, используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="043cd-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span></span>  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## <a name="using-the-imports-statement"></a><span data-ttu-id="043cd-105">Используя инструкцию Imports</span><span class="sxs-lookup"><span data-stu-id="043cd-105">Using the Imports Statement</span></span>  
 <span data-ttu-id="043cd-106">Можно избежать с помощью полных имен, добавив `Imports` инструкции в раздел объявлений пространства имен в коде, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="043cd-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 <span data-ttu-id="043cd-107">`Imports` Инструкция импортирует имена пространств имен из указанных проектов и сборок, а также из того же проекта, модуль, в котором находится данный оператор.</span><span class="sxs-lookup"><span data-stu-id="043cd-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span></span> <span data-ttu-id="043cd-108">После добавления этой инструкции можно ссылаться к членам перечисления без квалификации, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="043cd-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 <span data-ttu-id="043cd-109">Организуя наборы связанных констант в перечисления, можно использовать то же имя константы в различных контекстах.</span><span class="sxs-lookup"><span data-stu-id="043cd-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span></span> <span data-ttu-id="043cd-110">Например, можно использовать те же имена для констант дней недели в `Days` и `WorkDays` перечисления.</span><span class="sxs-lookup"><span data-stu-id="043cd-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span></span> <span data-ttu-id="043cd-111">Если вы используете `Imports` инструкции с перечислениями Будьте внимательны, чтобы избежать неоднозначных ссылок.</span><span class="sxs-lookup"><span data-stu-id="043cd-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span></span> <span data-ttu-id="043cd-112">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="043cd-112">Consider the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 <span data-ttu-id="043cd-113">Предположим, что `Monday` является одновременно членом групп `Days` перечисления и `Workdays` перечисления, этот код создает ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="043cd-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span></span> <span data-ttu-id="043cd-114">Чтобы избежать неоднозначности при ссылке на отдельную константу, уточните имя константы перечисления.</span><span class="sxs-lookup"><span data-stu-id="043cd-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span></span> <span data-ttu-id="043cd-115">Следующий код ссылается на `Saturday` констант в `Days` и `WorkDays` перечисления.</span><span class="sxs-lookup"><span data-stu-id="043cd-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span></span>  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="043cd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="043cd-116">See Also</span></span>  
 [<span data-ttu-id="043cd-117">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="043cd-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="043cd-118">Как: объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="043cd-118">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="043cd-119">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="043cd-119">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="043cd-120">Как: перебор элементов перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="043cd-120">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="043cd-121">Практическое руководство. Определение строки, связанной со значением из перечисления</span><span class="sxs-lookup"><span data-stu-id="043cd-121">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="043cd-122">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="043cd-122">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="043cd-123">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="043cd-123">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="043cd-124">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="043cd-124">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="043cd-125">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="043cd-125">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="043cd-126">Типы данных</span><span class="sxs-lookup"><span data-stu-id="043cd-126">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
