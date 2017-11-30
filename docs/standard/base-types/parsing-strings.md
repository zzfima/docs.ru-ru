---
title: "Анализ строк в .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 811db42e04e73d7acbc03e303297b19fdf643384
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="ba2a2-102">Анализ строк в .NET</span><span class="sxs-lookup"><span data-stu-id="ba2a2-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="ba2a2-103">Операция синтаксического анализа преобразует строку, представляющую базовый тип .NET, в этот базовый тип.</span><span class="sxs-lookup"><span data-stu-id="ba2a2-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="ba2a2-104">Например, операция синтаксического анализа используется для преобразования строки в число с плавающей запятой или в значение даты и времени.</span><span class="sxs-lookup"><span data-stu-id="ba2a2-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="ba2a2-105">Чаще всего для выполнения операции синтаксического разбора используется метод `Parse`.</span><span class="sxs-lookup"><span data-stu-id="ba2a2-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="ba2a2-106">Поскольку разбор — это операция, обратная форматированию (которое подразумевает преобразование базового типа в строковое представление), то применимы многие схожие правила и условия.</span><span class="sxs-lookup"><span data-stu-id="ba2a2-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="ba2a2-107">Точно так же, как при форматировании используется объект, реализующий <xref:System.IFormatProvider> интерфейс, предоставляющий язык и региональные параметры сведения о форматировании, при синтаксическом разборе используется объект, реализующий интерфейс <xref:System.IFormatProvider> интерфейс, чтобы определить, как интерпретировать строковое представление .</span><span class="sxs-lookup"><span data-stu-id="ba2a2-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="ba2a2-108">Дополнительные сведения см. в разделе [типы форматирования](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="ba2a2-108">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba2a2-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="ba2a2-109">In This Section</span></span>  
 [<span data-ttu-id="ba2a2-110">Анализ числовых строк</span><span class="sxs-lookup"><span data-stu-id="ba2a2-110">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)  
 <span data-ttu-id="ba2a2-111">Описывает способ преобразования строк в числовые типы .NET.</span><span class="sxs-lookup"><span data-stu-id="ba2a2-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="ba2a2-112">Анализ строк даты и времени</span><span class="sxs-lookup"><span data-stu-id="ba2a2-112">Parsing Date and Time Strings</span></span>](../../../docs/standard/base-types/parsing-datetime.md)  
 <span data-ttu-id="ba2a2-113">Описывает способ преобразования строк в .NET **DateTime** типов.</span><span class="sxs-lookup"><span data-stu-id="ba2a2-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="ba2a2-114">Анализ других строк</span><span class="sxs-lookup"><span data-stu-id="ba2a2-114">Parsing Other Strings</span></span>](../../../docs/standard/base-types/parsing-other.md)  
 <span data-ttu-id="ba2a2-115">Содержит сведения о преобразовании строк в **Char**, **логическое**, и **перечисления** типов.</span><span class="sxs-lookup"><span data-stu-id="ba2a2-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ba2a2-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ba2a2-116">Related Sections</span></span>  
 [<span data-ttu-id="ba2a2-117">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="ba2a2-117">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="ba2a2-118">Описывает базовые понятия форматирования, такие как описатели формата и Поставщики формата.</span><span class="sxs-lookup"><span data-stu-id="ba2a2-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="ba2a2-119">Преобразование типов в .NET</span><span class="sxs-lookup"><span data-stu-id="ba2a2-119">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="ba2a2-120">Описывает способ преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="ba2a2-120">Describes how to convert types.</span></span>  
  
 [<span data-ttu-id="ba2a2-121">Базовые типы</span><span class="sxs-lookup"><span data-stu-id="ba2a2-121">Base Types</span></span>](../../../docs/standard/base-types/index.md)  
 <span data-ttu-id="ba2a2-122">Описание распространенных операций, которые можно выполнять с базовыми типами .NET.</span><span class="sxs-lookup"><span data-stu-id="ba2a2-122">Describes common operations that you can perform on .NET base types.</span></span>
