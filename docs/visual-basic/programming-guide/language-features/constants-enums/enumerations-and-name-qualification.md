---
title: "Перечисления и уточнение имен (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cb97d6a8f4b7e81f2b759010214e200ec63ff21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="enumerations-and-name-qualification-visual-basic"></a><span data-ttu-id="bd2a1-102">Перечисления и уточнение имен (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd2a1-102">Enumerations and Name Qualification (Visual Basic)</span></span>
<span data-ttu-id="bd2a1-103">Обычно при ссылке на член перечисления необходимо уточнить имя члена перечисления.</span><span class="sxs-lookup"><span data-stu-id="bd2a1-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span></span> <span data-ttu-id="bd2a1-104">Например, для обращения к `Sunday` членом вашей `Days` перечисления, используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bd2a1-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span></span>  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## <a name="using-the-imports-statement"></a><span data-ttu-id="bd2a1-105">Используя инструкцию Imports</span><span class="sxs-lookup"><span data-stu-id="bd2a1-105">Using the Imports Statement</span></span>  
 <span data-ttu-id="bd2a1-106">Можно избежать с помощью полных имен, добавив `Imports` инструкции в раздел объявлений пространства имен в коде, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd2a1-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 <span data-ttu-id="bd2a1-107">`Imports` Инструкция импортирует имена пространств имен из указанных проектов и сборок, а также из того же проекта, модуль, в котором находится данный оператор.</span><span class="sxs-lookup"><span data-stu-id="bd2a1-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span></span> <span data-ttu-id="bd2a1-108">После добавления этой инструкции можно ссылаться к членам перечисления без квалификации, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd2a1-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 <span data-ttu-id="bd2a1-109">Организуя наборы связанных констант в перечисления, можно использовать то же имя константы в различных контекстах.</span><span class="sxs-lookup"><span data-stu-id="bd2a1-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span></span> <span data-ttu-id="bd2a1-110">Например, можно использовать те же имена для констант дней недели в `Days` и `WorkDays` перечисления.</span><span class="sxs-lookup"><span data-stu-id="bd2a1-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span></span> <span data-ttu-id="bd2a1-111">Если вы используете `Imports` инструкции с перечислениями Будьте внимательны, чтобы избежать неоднозначных ссылок.</span><span class="sxs-lookup"><span data-stu-id="bd2a1-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span></span> <span data-ttu-id="bd2a1-112">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="bd2a1-112">Consider the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 <span data-ttu-id="bd2a1-113">Предположим, что `Monday` является одновременно членом групп `Days` перечисления и `Workdays` перечисления, этот код создает ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="bd2a1-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span></span> <span data-ttu-id="bd2a1-114">Чтобы избежать неоднозначности при ссылке на отдельную константу, уточните имя константы перечисления.</span><span class="sxs-lookup"><span data-stu-id="bd2a1-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span></span> <span data-ttu-id="bd2a1-115">Следующий код ссылается на `Saturday` констант в `Days` и `WorkDays` перечисления.</span><span class="sxs-lookup"><span data-stu-id="bd2a1-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span></span>  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bd2a1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bd2a1-116">See Also</span></span>  
 [<span data-ttu-id="bd2a1-117">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="bd2a1-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="bd2a1-118">Как: объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="bd2a1-118">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="bd2a1-119">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="bd2a1-119">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="bd2a1-120">Как: перебор элементов перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd2a1-120">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="bd2a1-121">Практическое руководство. Определение строки, связанной со значением из перечисления</span><span class="sxs-lookup"><span data-stu-id="bd2a1-121">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="bd2a1-122">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="bd2a1-122">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="bd2a1-123">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="bd2a1-123">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="bd2a1-124">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="bd2a1-124">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="bd2a1-125">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="bd2a1-125">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="bd2a1-126">Типы данных</span><span class="sxs-lookup"><span data-stu-id="bd2a1-126">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
