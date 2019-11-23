---
title: Преобразования типов
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
ms.openlocfilehash: fbf0c9877cf9a9b4364c8c058c61e847ad7bf049
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348723"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="68c31-102">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="68c31-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="68c31-103">The process of changing a value from one data type to another type is called *conversion*.</span><span class="sxs-lookup"><span data-stu-id="68c31-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="68c31-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span><span class="sxs-lookup"><span data-stu-id="68c31-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="68c31-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span><span class="sxs-lookup"><span data-stu-id="68c31-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68c31-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="68c31-106">In This Section</span></span>  
 [<span data-ttu-id="68c31-107">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="68c31-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="68c31-108">Explains conversions classified by whether the destination type can hold the data.</span><span class="sxs-lookup"><span data-stu-id="68c31-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="68c31-109">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="68c31-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="68c31-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span><span class="sxs-lookup"><span data-stu-id="68c31-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="68c31-111">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="68c31-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="68c31-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span><span class="sxs-lookup"><span data-stu-id="68c31-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="68c31-113">How to: Convert an Object to Another Type in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="68c31-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="68c31-114">Shows how to convert an `Object` variable to any other data type.</span><span class="sxs-lookup"><span data-stu-id="68c31-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="68c31-115">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="68c31-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="68c31-116">Steps you through the process of converting between arrays of different data types.</span><span class="sxs-lookup"><span data-stu-id="68c31-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="68c31-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="68c31-117">Related Sections</span></span>  
 [<span data-ttu-id="68c31-118">Типы данных</span><span class="sxs-lookup"><span data-stu-id="68c31-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="68c31-119">Introduces the Visual Basic data types and describes how to use them.</span><span class="sxs-lookup"><span data-stu-id="68c31-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="68c31-120">Типы данных</span><span class="sxs-lookup"><span data-stu-id="68c31-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 <span data-ttu-id="68c31-121">Lists the elementary data types supplied by Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="68c31-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="68c31-122">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="68c31-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="68c31-123">Discusses some common problems that can arise when working with data types.</span><span class="sxs-lookup"><span data-stu-id="68c31-123">Discusses some common problems that can arise when working with data types.</span></span>
