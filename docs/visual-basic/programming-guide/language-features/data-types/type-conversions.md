---
title: "Преобразование типов в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- conversions, type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion
- conversions, data type
- changing data types
- data type conversion
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 61606572dd1f10dc5df4ed4baec02f230a23c8d6
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="c9c56-102">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9c56-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="c9c56-103">Процесс приведения значения одного типа данных к другому типу называется *преобразование*.</span><span class="sxs-lookup"><span data-stu-id="c9c56-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="c9c56-104">Преобразования, либо *расширяющие* или *сужающие*, в зависимости от диапазонов данных типов.</span><span class="sxs-lookup"><span data-stu-id="c9c56-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="c9c56-105">Они также *неявное* или *явных*в зависимости от синтаксиса в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="c9c56-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9c56-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="c9c56-106">In This Section</span></span>  
 [<span data-ttu-id="c9c56-107">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="c9c56-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="c9c56-108">Описание преобразований, различающихся по ли целевой тип может содержать данные.</span><span class="sxs-lookup"><span data-stu-id="c9c56-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="c9c56-109">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="c9c56-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="c9c56-110">Описываются преобразования, классифицируется ли [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] их автоматического выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9c56-110">Discusses conversions classified by whether [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] performs them automatically.</span></span>  
  
 [<span data-ttu-id="c9c56-111">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="c9c56-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="c9c56-112">Описываются преобразования между строками и числовыми, `Boolean`, или значения даты и времени.</span><span class="sxs-lookup"><span data-stu-id="c9c56-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="c9c56-113">Практическое руководство: преобразование объекта к другому типу в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9c56-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="c9c56-114">Показано, как преобразовать `Object` переменной другого типа данных.</span><span class="sxs-lookup"><span data-stu-id="c9c56-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="c9c56-115">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="c9c56-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="c9c56-116">Этапы процесса преобразования между массивами различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="c9c56-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c9c56-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c9c56-117">Related Sections</span></span>  
 [<span data-ttu-id="c9c56-118">Типы данных</span><span class="sxs-lookup"><span data-stu-id="c9c56-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="c9c56-119">Представляет [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] типы данных и инструкции по их использованию.</span><span class="sxs-lookup"><span data-stu-id="c9c56-119">Introduces the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="c9c56-120">Типы данных</span><span class="sxs-lookup"><span data-stu-id="c9c56-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="c9c56-121">Список простых типов данных предоставляемые [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9c56-121">Lists the elementary data types supplied by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 [<span data-ttu-id="c9c56-122">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="c9c56-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="c9c56-123">Рассматриваются некоторые общие проблемы, которые могут возникнуть при работе с типами данных.</span><span class="sxs-lookup"><span data-stu-id="c9c56-123">Discusses some common problems that can arise when working with data types.</span></span>
