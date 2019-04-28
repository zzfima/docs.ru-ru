---
title: Возвращаемые значения функции CStr (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 3653194c7e48533e664ac7513ca7f4f48d1c69f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801534"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="9e6ca-102">Возвращаемые значения функции CStr (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e6ca-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="9e6ca-103">В следующей таблице описаны возвращаемые значения для `CStr` для различных типов данных из `expression`.</span><span class="sxs-lookup"><span data-stu-id="9e6ca-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="9e6ca-104">Если `expression` тип —</span><span class="sxs-lookup"><span data-stu-id="9e6ca-104">If `expression` type is</span></span>|<span data-ttu-id="9e6ca-105">Возвращаемые значения `CStr`</span><span class="sxs-lookup"><span data-stu-id="9e6ca-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="9e6ca-106">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="9e6ca-106">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="9e6ca-107">Строка, содержащая «True» или «False».</span><span class="sxs-lookup"><span data-stu-id="9e6ca-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="9e6ca-108">Тип данных Date</span><span class="sxs-lookup"><span data-stu-id="9e6ca-108">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="9e6ca-109">Строка, содержащая `Date` значение (Дата и время) в формате короткой даты системы.</span><span class="sxs-lookup"><span data-stu-id="9e6ca-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="9e6ca-110">Числовые типы данных</span><span class="sxs-lookup"><span data-stu-id="9e6ca-110">Numeric Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="9e6ca-111">Строка, представляющая число.</span><span class="sxs-lookup"><span data-stu-id="9e6ca-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="9e6ca-112">CStr и даты</span><span class="sxs-lookup"><span data-stu-id="9e6ca-112">CStr and Date</span></span>  
 <span data-ttu-id="9e6ca-113">`Date` Тип всегда содержит сведения о дате и времени.</span><span class="sxs-lookup"><span data-stu-id="9e6ca-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="9e6ca-114">В целях преобразования типов Visual Basic рассматривает 1/1/0001 (1 января 1 года) быть *нейтральным значением* для даты и 00:00:00 (полночь) могла быть нейтральным значением времени.</span><span class="sxs-lookup"><span data-stu-id="9e6ca-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="9e6ca-115">`CStr` не включает нейтральные значения в результирующую строку.</span><span class="sxs-lookup"><span data-stu-id="9e6ca-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="9e6ca-116">Например, при преобразовании `#January 1, 0001 9:30:00#` в строку, результат равен «9:30:00 AM»; дата отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="9e6ca-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="9e6ca-117">Тем не менее, сведения о дате по-прежнему присутствует в исходном `Date` значение и могут быть извлечены с помощью функции например <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span><span class="sxs-lookup"><span data-stu-id="9e6ca-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e6ca-118">`CStr` Функция выполняет преобразование на основе текущих настроек языка и региональных параметров для приложения.</span><span class="sxs-lookup"><span data-stu-id="9e6ca-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="9e6ca-119">Чтобы получить строковое представление числа в определенного языка и региональных параметров, используйте номер `ToString(IFormatProvider)` метод.</span><span class="sxs-lookup"><span data-stu-id="9e6ca-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="9e6ca-120">Например, использовать <xref:System.Double.ToString%2A?displayProperty=nameWithType> при преобразовании значения типа `Double` для `String`.</span><span class="sxs-lookup"><span data-stu-id="9e6ca-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e6ca-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9e6ca-121">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="9e6ca-122">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="9e6ca-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="9e6ca-123">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="9e6ca-123">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="9e6ca-124">Тип данных Date</span><span class="sxs-lookup"><span data-stu-id="9e6ca-124">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)
