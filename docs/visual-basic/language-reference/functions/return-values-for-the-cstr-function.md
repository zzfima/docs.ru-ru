---
title: "Возвращаемые значения функции CStr (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b498c9b1b7916467c96ed2c645c7131192a5e8b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="44ea6-102">Возвращаемые значения функции CStr (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44ea6-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="44ea6-103">В следующей таблице описаны возвращаемые значения для `CStr` для различных типов данных из `expression`.</span><span class="sxs-lookup"><span data-stu-id="44ea6-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="44ea6-104">Если `expression` тип</span><span class="sxs-lookup"><span data-stu-id="44ea6-104">If `expression` type is</span></span>|<span data-ttu-id="44ea6-105">`CStr`Возвращает</span><span class="sxs-lookup"><span data-stu-id="44ea6-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="44ea6-106">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="44ea6-106">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="44ea6-107">Строка, содержащая «True» или «False».</span><span class="sxs-lookup"><span data-stu-id="44ea6-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="44ea6-108">Тип данных Date</span><span class="sxs-lookup"><span data-stu-id="44ea6-108">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="44ea6-109">Строка, содержащая `Date` значение (Дата и время) в формате короткой даты системы.</span><span class="sxs-lookup"><span data-stu-id="44ea6-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="44ea6-110">Числовые типы данных</span><span class="sxs-lookup"><span data-stu-id="44ea6-110">Numeric Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="44ea6-111">Строка, содержащая число.</span><span class="sxs-lookup"><span data-stu-id="44ea6-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="44ea6-112">CStr и даты</span><span class="sxs-lookup"><span data-stu-id="44ea6-112">CStr and Date</span></span>  
 <span data-ttu-id="44ea6-113">`Date` Типа всегда содержит сведения о дате и времени.</span><span class="sxs-lookup"><span data-stu-id="44ea6-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="44ea6-114">В целях преобразования типов Visual Basic рассматривает 1/1/0001 (1 января 1 года) быть *нейтральным значением* для даты и 00:00:00 (полночь) будет нейтральным значением времени.</span><span class="sxs-lookup"><span data-stu-id="44ea6-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="44ea6-115">`CStr`не включает нейтральные значения в результирующую строку.</span><span class="sxs-lookup"><span data-stu-id="44ea6-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="44ea6-116">Например, если вы преобразуете `#January 1, 0001 9:30:00#` в строку, результат будет «9:30:00 AM»; дата отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="44ea6-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="44ea6-117">Тем не менее, сведения о дате по-прежнему присутствует в исходной коллекции `Date` значение и может быть восстановлен с помощью функции например <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span><span class="sxs-lookup"><span data-stu-id="44ea6-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44ea6-118">`CStr` Функция выполняет преобразование на основе текущих параметров языка и региональных параметров для приложения.</span><span class="sxs-lookup"><span data-stu-id="44ea6-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="44ea6-119">Чтобы получить строковое представление числа в определенного языка и региональных параметров, используйте число `ToString(IFormatProvider)` метод.</span><span class="sxs-lookup"><span data-stu-id="44ea6-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="44ea6-120">Например, использовать <xref:System.Double.ToString%2A?displayProperty=nameWithType> при преобразовании значения типа `Double` для `String`.</span><span class="sxs-lookup"><span data-stu-id="44ea6-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44ea6-121">См. также</span><span class="sxs-lookup"><span data-stu-id="44ea6-121">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>  
 [<span data-ttu-id="44ea6-122">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="44ea6-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="44ea6-123">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="44ea6-123">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [<span data-ttu-id="44ea6-124">Тип данных Date</span><span class="sxs-lookup"><span data-stu-id="44ea6-124">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)
