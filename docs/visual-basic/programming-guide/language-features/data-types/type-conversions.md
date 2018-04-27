---
title: Преобразование типов в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f1487d98f37e7ef00982de365d0d164435f84567
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="a56c8-102">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a56c8-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="a56c8-103">Процесс изменения типа значения из одного типа данных к другому типу называется *преобразование*.</span><span class="sxs-lookup"><span data-stu-id="a56c8-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="a56c8-104">Преобразования являются либо *расширяющие* или *сужающие*, в зависимости от диапазонов данных типов.</span><span class="sxs-lookup"><span data-stu-id="a56c8-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="a56c8-105">Они также могут *неявное* или *явных*, в зависимости от синтаксиса в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="a56c8-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a56c8-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a56c8-106">In This Section</span></span>  
 [<span data-ttu-id="a56c8-107">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="a56c8-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="a56c8-108">Описание преобразований, различающихся по ли целевой тип может содержать данные.</span><span class="sxs-lookup"><span data-stu-id="a56c8-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="a56c8-109">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="a56c8-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="a56c8-110">Описываются преобразования, классифицированные по возможности их автоматического выполнения в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a56c8-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="a56c8-111">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="a56c8-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="a56c8-112">Описываются преобразования между строками и числовыми, `Boolean`, или значения даты и времени.</span><span class="sxs-lookup"><span data-stu-id="a56c8-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="a56c8-113">Как: преобразование объекта к другому типу в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a56c8-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="a56c8-114">Показано, как преобразовать `Object` в любой другой тип данных переменной.</span><span class="sxs-lookup"><span data-stu-id="a56c8-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="a56c8-115">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="a56c8-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="a56c8-116">Этапы процесса преобразования между массивами различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="a56c8-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a56c8-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a56c8-117">Related Sections</span></span>  
 [<span data-ttu-id="a56c8-118">Типы данных</span><span class="sxs-lookup"><span data-stu-id="a56c8-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="a56c8-119">Знакомство с типами данных Visual Basic и описывается их использование.</span><span class="sxs-lookup"><span data-stu-id="a56c8-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="a56c8-120">Типы данных</span><span class="sxs-lookup"><span data-stu-id="a56c8-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="a56c8-121">Список простейших типов данных в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a56c8-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="a56c8-122">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="a56c8-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="a56c8-123">Рассматриваются некоторые общие проблемы, которые могут возникнуть при работе с типами данных.</span><span class="sxs-lookup"><span data-stu-id="a56c8-123">Discusses some common problems that can arise when working with data types.</span></span>
