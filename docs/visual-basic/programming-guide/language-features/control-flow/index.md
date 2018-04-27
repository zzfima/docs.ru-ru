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
ms.openlocfilehash: 4ec3ab191942e47d5025a0e641085b0f507088c7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="control-flow-in-visual-basic"></a><span data-ttu-id="25d0d-102">Управление ходом выполнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="25d0d-102">Control Flow in Visual Basic</span></span>
<span data-ttu-id="25d0d-103">При отсутствии вмешательства извне программа последовательно выполняет все свои инструкции от начала до конца.</span><span class="sxs-lookup"><span data-stu-id="25d0d-103">Left unregulated, a program proceeds through its statements from beginning to end.</span></span> <span data-ttu-id="25d0d-104">Некоторые очень простые программы могут быть написаны только с таким однонаправленным потоком.</span><span class="sxs-lookup"><span data-stu-id="25d0d-104">Some very simple programs can be written with only this unidirectional flow.</span></span> <span data-ttu-id="25d0d-105">Но мощь и преимущества любого языка программирования в значительной степени связаны с возможностями изменения порядка выполнения с помощью операторов управления и циклов.</span><span class="sxs-lookup"><span data-stu-id="25d0d-105">However, much of the power and utility of any programming language comes from the ability to change execution order with control statements and loops.</span></span>  
  
 <span data-ttu-id="25d0d-106">Структуры управления позволяют контролировать поток выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="25d0d-106">Control structures allow you to regulate the flow of your program's execution.</span></span> <span data-ttu-id="25d0d-107">С помощью структур управления, можно писать код Visual Basic, который принимает решения или повторяет действия.</span><span class="sxs-lookup"><span data-stu-id="25d0d-107">Using control structures, you can write Visual Basic code that makes decisions or that repeats actions.</span></span> <span data-ttu-id="25d0d-108">Другие структуры управления позволяют обеспечивать гарантированное удаление ресурса или запускать серию операторов для одной ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="25d0d-108">Other control structures let you guarantee disposal of a resource or run a series of statements on the same object reference.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="25d0d-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="25d0d-109">In This Section</span></span>  
 [<span data-ttu-id="25d0d-110">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="25d0d-110">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 <span data-ttu-id="25d0d-111">Содержит описание структур управления, используемых для ветвления.</span><span class="sxs-lookup"><span data-stu-id="25d0d-111">Describes control structures used for branching.</span></span>  
  
 [<span data-ttu-id="25d0d-112">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="25d0d-112">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 <span data-ttu-id="25d0d-113">Содержит описание структур управления, используемых для повторения процессов.</span><span class="sxs-lookup"><span data-stu-id="25d0d-113">Discusses control structures used to repeat processes.</span></span>  
  
 [<span data-ttu-id="25d0d-114">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="25d0d-114">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 <span data-ttu-id="25d0d-115">Содержит описание структур управления, используемых для освобождения ресурсов и доступа к объектам.</span><span class="sxs-lookup"><span data-stu-id="25d0d-115">Describes control structures used for resource disposal and object access.</span></span>  
  
 [<span data-ttu-id="25d0d-116">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="25d0d-116">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 <span data-ttu-id="25d0d-117">Содержит описание структур управления, находящихся внутри других структур управления.</span><span class="sxs-lookup"><span data-stu-id="25d0d-117">Covers control structures inside other control structures.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="25d0d-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="25d0d-118">Related Sections</span></span>  
 [<span data-ttu-id="25d0d-119">Сводка по управлению ходом выполнения</span><span class="sxs-lookup"><span data-stu-id="25d0d-119">Control Flow Summary</span></span>](../../../../visual-basic/language-reference/keywords/control-flow-summary.md)  
 <span data-ttu-id="25d0d-120">Содержит ссылки на разделы справочника по языку, посвященные этой теме.</span><span class="sxs-lookup"><span data-stu-id="25d0d-120">Provides links to language reference pages on this subject.</span></span>
