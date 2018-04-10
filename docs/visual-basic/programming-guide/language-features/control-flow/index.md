---
title: Управление ходом выполнения в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- control flow [Visual Basic]
- control structures [Visual Basic]
- structures [Visual Basic], control
- conditional statements [Visual Basic], control flow
ms.assetid: 5623ef47-52b1-4202-befd-9af36422ec6f
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ce0cb7cba8f05b488d47f99da51b0b5de75eb15
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="control-flow-in-visual-basic"></a><span data-ttu-id="8c971-102">Управление ходом выполнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c971-102">Control Flow in Visual Basic</span></span>
<span data-ttu-id="8c971-103">При отсутствии вмешательства извне программа последовательно выполняет все свои инструкции от начала до конца.</span><span class="sxs-lookup"><span data-stu-id="8c971-103">Left unregulated, a program proceeds through its statements from beginning to end.</span></span> <span data-ttu-id="8c971-104">Некоторые очень простые программы могут быть написаны только с таким однонаправленным потоком.</span><span class="sxs-lookup"><span data-stu-id="8c971-104">Some very simple programs can be written with only this unidirectional flow.</span></span> <span data-ttu-id="8c971-105">Но мощь и преимущества любого языка программирования в значительной степени связаны с возможностями изменения порядка выполнения с помощью операторов управления и циклов.</span><span class="sxs-lookup"><span data-stu-id="8c971-105">However, much of the power and utility of any programming language comes from the ability to change execution order with control statements and loops.</span></span>  
  
 <span data-ttu-id="8c971-106">Структуры управления позволяют контролировать поток выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="8c971-106">Control structures allow you to regulate the flow of your program's execution.</span></span> <span data-ttu-id="8c971-107">С помощью структур управления можно написать код [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], который принимает решения или повторяет определенные действия.</span><span class="sxs-lookup"><span data-stu-id="8c971-107">Using control structures, you can write [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code that makes decisions or that repeats actions.</span></span> <span data-ttu-id="8c971-108">Другие структуры управления позволяют обеспечивать гарантированное удаление ресурса или запускать серию операторов для одной ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="8c971-108">Other control structures let you guarantee disposal of a resource or run a series of statements on the same object reference.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c971-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="8c971-109">In This Section</span></span>  
 [<span data-ttu-id="8c971-110">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="8c971-110">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 <span data-ttu-id="8c971-111">Содержит описание структур управления, используемых для ветвления.</span><span class="sxs-lookup"><span data-stu-id="8c971-111">Describes control structures used for branching.</span></span>  
  
 [<span data-ttu-id="8c971-112">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="8c971-112">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 <span data-ttu-id="8c971-113">Содержит описание структур управления, используемых для повторения процессов.</span><span class="sxs-lookup"><span data-stu-id="8c971-113">Discusses control structures used to repeat processes.</span></span>  
  
 [<span data-ttu-id="8c971-114">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="8c971-114">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 <span data-ttu-id="8c971-115">Содержит описание структур управления, используемых для освобождения ресурсов и доступа к объектам.</span><span class="sxs-lookup"><span data-stu-id="8c971-115">Describes control structures used for resource disposal and object access.</span></span>  
  
 [<span data-ttu-id="8c971-116">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="8c971-116">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 <span data-ttu-id="8c971-117">Содержит описание структур управления, находящихся внутри других структур управления.</span><span class="sxs-lookup"><span data-stu-id="8c971-117">Covers control structures inside other control structures.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8c971-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="8c971-118">Related Sections</span></span>  
 [<span data-ttu-id="8c971-119">Сводка по управлению ходом выполнения</span><span class="sxs-lookup"><span data-stu-id="8c971-119">Control Flow Summary</span></span>](../../../../visual-basic/language-reference/keywords/control-flow-summary.md)  
 <span data-ttu-id="8c971-120">Содержит ссылки на разделы справочника по языку, посвященные этой теме.</span><span class="sxs-lookup"><span data-stu-id="8c971-120">Provides links to language reference pages on this subject.</span></span>
