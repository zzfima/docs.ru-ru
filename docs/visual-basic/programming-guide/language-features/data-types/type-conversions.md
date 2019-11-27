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
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="9d408-102">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9d408-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="9d408-103">Процесс изменения значения из одного типа данных на другой тип называется *преобразованием*.</span><span class="sxs-lookup"><span data-stu-id="9d408-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="9d408-104">Преобразования могут *расширяться* или *уменьшаться*в зависимости от объема данных используемых типов.</span><span class="sxs-lookup"><span data-stu-id="9d408-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="9d408-105">Они также являются *неявно* илиявными в зависимости от синтаксиса в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="9d408-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d408-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="9d408-106">In This Section</span></span>  
 [<span data-ttu-id="9d408-107">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="9d408-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="9d408-108">Описывает преобразования, классифицированные, если целевой тип может содержать данные.</span><span class="sxs-lookup"><span data-stu-id="9d408-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="9d408-109">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="9d408-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="9d408-110">Описывает преобразования, которые классифицируются, независимо от того, выполняет ли Visual Basic их автоматически.</span><span class="sxs-lookup"><span data-stu-id="9d408-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="9d408-111">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="9d408-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="9d408-112">Демонстрирует преобразование между строками и числовыми, `Boolean`или значениями даты и времени.</span><span class="sxs-lookup"><span data-stu-id="9d408-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="9d408-113">Как преобразовать объект в другой тип в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9d408-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="9d408-114">Показывает, как преобразовать переменную `Object` в любой другой тип данных.</span><span class="sxs-lookup"><span data-stu-id="9d408-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="9d408-115">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="9d408-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="9d408-116">Пошаговый процесс преобразования между массивами различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="9d408-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9d408-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9d408-117">Related Sections</span></span>  
 [<span data-ttu-id="9d408-118">Типы данных</span><span class="sxs-lookup"><span data-stu-id="9d408-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="9d408-119">Вводит Visual Basic типы данных и описывает, как их использовать.</span><span class="sxs-lookup"><span data-stu-id="9d408-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="9d408-120">Типы данных</span><span class="sxs-lookup"><span data-stu-id="9d408-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 <span data-ttu-id="9d408-121">Содержит список простейших типов данных, предоставляемых Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9d408-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="9d408-122">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="9d408-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="9d408-123">Обсуждаются некоторые распространенные проблемы, которые могут возникнуть при работе с типами данных.</span><span class="sxs-lookup"><span data-stu-id="9d408-123">Discusses some common problems that can arise when working with data types.</span></span>
