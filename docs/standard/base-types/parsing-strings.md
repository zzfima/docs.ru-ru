---
title: Анализ строк в .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: 717022e5d2e292c1624e6155bd7571e4daa997b9
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523804"
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="8ddda-102">Анализ строк в .NET</span><span class="sxs-lookup"><span data-stu-id="8ddda-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="8ddda-103">Операция синтаксического анализа преобразует строку, представляющую базовый тип .NET, в этот базовый тип.</span><span class="sxs-lookup"><span data-stu-id="8ddda-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="8ddda-104">Например, операция синтаксического анализа используется для преобразования строки в число с плавающей запятой или в значение даты и времени.</span><span class="sxs-lookup"><span data-stu-id="8ddda-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="8ddda-105">Чаще всего для выполнения операции синтаксического разбора используется метод `Parse`.</span><span class="sxs-lookup"><span data-stu-id="8ddda-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="8ddda-106">Поскольку разбор — это операция, обратная форматированию (которое подразумевает преобразование базового типа в строковое представление), то применимы многие схожие правила и условия.</span><span class="sxs-lookup"><span data-stu-id="8ddda-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="8ddda-107">Подобно тому, как при форматировании используется объект, реализующий интерфейс <xref:System.IFormatProvider> для предоставления зависящей от языка и региональных параметров информации форматирования, точно так же и при синтаксическом разборе используется объект, реализующий интерфейс <xref:System.IFormatProvider>, чтобы определить, как интерпретировать строковое представление.</span><span class="sxs-lookup"><span data-stu-id="8ddda-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="8ddda-108">Дополнительные сведения см. в статье [Типы форматирования в .NET](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="8ddda-108">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ddda-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="8ddda-109">In This Section</span></span>  
 [<span data-ttu-id="8ddda-110">Анализ числовых строк</span><span class="sxs-lookup"><span data-stu-id="8ddda-110">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)  
 <span data-ttu-id="8ddda-111">Описание преобразования строк в числовые типы .NET.</span><span class="sxs-lookup"><span data-stu-id="8ddda-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="8ddda-112">Анализ строк даты и времени</span><span class="sxs-lookup"><span data-stu-id="8ddda-112">Parsing Date and Time Strings</span></span>](../../../docs/standard/base-types/parsing-datetime.md)  
 <span data-ttu-id="8ddda-113">Описание преобразования строк в типы **даты и времени** .NET.</span><span class="sxs-lookup"><span data-stu-id="8ddda-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="8ddda-114">Анализ других строк</span><span class="sxs-lookup"><span data-stu-id="8ddda-114">Parsing Other Strings</span></span>](../../../docs/standard/base-types/parsing-other.md)  
 <span data-ttu-id="8ddda-115">Описание преобразования строк в типы **Char**, **Boolean** и **Enum**.</span><span class="sxs-lookup"><span data-stu-id="8ddda-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8ddda-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="8ddda-116">Related Sections</span></span>  
 [<span data-ttu-id="8ddda-117">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="8ddda-117">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="8ddda-118">Описание базовых концепций форматирования, таких как описатели формата и поставщики формата.</span><span class="sxs-lookup"><span data-stu-id="8ddda-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="8ddda-119">Преобразование типов в .NET</span><span class="sxs-lookup"><span data-stu-id="8ddda-119">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="8ddda-120">Описание процесса преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="8ddda-120">Describes how to convert types.</span></span>
