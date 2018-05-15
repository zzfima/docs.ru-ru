---
title: Преобразование типов в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
ms.openlocfilehash: 7f1a571cda4f68222c5c03c3a8fe31c29eafd8c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="143aa-102">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="143aa-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="143aa-103">Процесс изменения типа значения из одного типа данных к другому типу называется *преобразование*.</span><span class="sxs-lookup"><span data-stu-id="143aa-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="143aa-104">Преобразования являются либо *расширяющие* или *сужающие*, в зависимости от диапазонов данных типов.</span><span class="sxs-lookup"><span data-stu-id="143aa-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="143aa-105">Они также могут *неявное* или *явных*, в зависимости от синтаксиса в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="143aa-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="143aa-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="143aa-106">In This Section</span></span>  
 [<span data-ttu-id="143aa-107">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="143aa-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="143aa-108">Описание преобразований, различающихся по ли целевой тип может содержать данные.</span><span class="sxs-lookup"><span data-stu-id="143aa-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="143aa-109">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="143aa-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="143aa-110">Описываются преобразования, классифицированные по возможности их автоматического выполнения в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="143aa-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="143aa-111">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="143aa-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="143aa-112">Описываются преобразования между строками и числовыми, `Boolean`, или значения даты и времени.</span><span class="sxs-lookup"><span data-stu-id="143aa-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="143aa-113">Как: преобразование объекта к другому типу в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="143aa-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="143aa-114">Показано, как преобразовать `Object` в любой другой тип данных переменной.</span><span class="sxs-lookup"><span data-stu-id="143aa-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="143aa-115">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="143aa-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="143aa-116">Этапы процесса преобразования между массивами различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="143aa-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="143aa-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="143aa-117">Related Sections</span></span>  
 [<span data-ttu-id="143aa-118">Типы данных</span><span class="sxs-lookup"><span data-stu-id="143aa-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="143aa-119">Знакомство с типами данных Visual Basic и описывается их использование.</span><span class="sxs-lookup"><span data-stu-id="143aa-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="143aa-120">Типы данных</span><span class="sxs-lookup"><span data-stu-id="143aa-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="143aa-121">Список простейших типов данных в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="143aa-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="143aa-122">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="143aa-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="143aa-123">Рассматриваются некоторые общие проблемы, которые могут возникнуть при работе с типами данных.</span><span class="sxs-lookup"><span data-stu-id="143aa-123">Discusses some common problems that can arise when working with data types.</span></span>
