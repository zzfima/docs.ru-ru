---
title: "Анализ строк в .NET"
description: "Анализ строк в .NET"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8103c0a6-61d3-40dd-a3e9-2a32ba6a4c05
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: c741ae793d491f691a355df6ad064b81d609c7e5
ms.contentlocale: ru-ru
ms.lasthandoff: 03/03/2017

---

# <a name="parsing-strings-in-net"></a><span data-ttu-id="409d0-104">Анализ строк в .NET</span><span class="sxs-lookup"><span data-stu-id="409d0-104">Parsing strings in .NET</span></span>

<span data-ttu-id="409d0-105">Операция синтаксического анализа преобразует строку, представляющую базовый тип .NET, в этот базовый тип.</span><span class="sxs-lookup"><span data-stu-id="409d0-105">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="409d0-106">Например, операция синтаксического анализа используется для преобразования строки в число с плавающей запятой или в значение даты и времени.</span><span class="sxs-lookup"><span data-stu-id="409d0-106">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="409d0-107">Чаще всего для выполнения операции синтаксического разбора используется метод `Parse`.</span><span class="sxs-lookup"><span data-stu-id="409d0-107">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="409d0-108">Поскольку разбор — это операция, обратная форматированию (которое подразумевает преобразование базового типа в строковое представление), то применимы многие схожие правила и условия.</span><span class="sxs-lookup"><span data-stu-id="409d0-108">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="409d0-109">Подобно тому, как при форматировании используется объект, реализующий интерфейс [IFormatProvider](xref:System.IFormatProvider) для предоставления зависящей от языка и региональных параметров информации форматирования, точно так же и при синтаксическом разборе используется объект, реализующий интерфейс [IFormatProvider](xref:System.IFormatProvider), чтобы определить, как интерпретировать строковое представление.</span><span class="sxs-lookup"><span data-stu-id="409d0-109">Just as formatting uses an object that implements the [IFormatProvider](xref:System.IFormatProvider) interface to provide culture-sensitive formatting information, parsing also uses an object that implements the [IFormatProvider](xref:System.IFormatProvider) interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="409d0-110">Дополнительные сведения см. в разделе [Типы форматирования в .NET](formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="409d0-110">For more information, see [Formatting Types in .NET](formatting-types.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="409d0-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="409d0-111">In This Section</span></span>

<span data-ttu-id="409d0-112">[Анализ числовых строк в .NET](parsing-numeric.md) — описание преобразования строк в числовые типы .NET.</span><span class="sxs-lookup"><span data-stu-id="409d0-112">[Parsing Numeric Strings in .NET](parsing-numeric.md) - Describes how to convert strings into .NET numeric types.</span></span>

<span data-ttu-id="409d0-113">[Анализ строк даты и времени в .NET](parsing-datetime.md) — описание преобразования строк в типы `DateTime` .NET.</span><span class="sxs-lookup"><span data-stu-id="409d0-113">[Parsing Date and Time Strings in .NET](parsing-datetime.md) - Describes how to convert strings into .NET `DateTime` types.</span></span>

<span data-ttu-id="409d0-114">[Анализ других строк в .NET](parsing-other.md) — описание преобразования строк в типы [Char](xref:System.Char), [Boolean](xref:System.Boolean) и [Enum](xref:System.Enum).</span><span class="sxs-lookup"><span data-stu-id="409d0-114">[Parsing Other Strings in .NET](parsing-other.md) - Describes how to convert strings into [Char](xref:System.Char), [Boolean](xref:System.Boolean), and [Enum](xref:System.Enum) types.</span></span>

<span data-ttu-id="409d0-115">[Типы форматирования в .NET](formatting-types.md) — описание базовых понятий форматирования, таких как описатели и поставщики формата.</span><span class="sxs-lookup"><span data-stu-id="409d0-115">[Formatting Types in .NET](formatting-types.md) - Describes basic formatting concepts like format specifiers and format providers.</span></span>

<span data-ttu-id="409d0-116">[Преобразование типов в .NET](type-conversion.md) — описание способов преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="409d0-116">[Type Conversion in .NET](type-conversion.md) - Describes how to convert types.</span></span>

<span data-ttu-id="409d0-117">[Работа с базовыми типами в .NET](index.md) — описание общих операций, которые можно выполнять с базовыми типами .NET.</span><span class="sxs-lookup"><span data-stu-id="409d0-117">[Working with Base Types in .NET](index.md) - Describes common operations that you can perform on .NET base types.</span></span>


