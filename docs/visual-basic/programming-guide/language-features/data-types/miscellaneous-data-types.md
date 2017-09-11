---
title: "Прочие типы данных (Visual Basic) | Документы Microsoft"
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
- Object data type, data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
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
ms.openlocfilehash: ed7b61a5ec57ff85347f2c257e321ab9ec425274
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="c78e9-102">Прочие типы данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c78e9-102">Miscellaneous Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="c78e9-103">имеется несколько типов данных, не предназначенных для чисел или знаков.</span><span class="sxs-lookup"><span data-stu-id="c78e9-103"> supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="c78e9-104">Они предусмотрены для настраиваемых данных, таких как логический значений, значений даты и времени и адресов объектов.</span><span class="sxs-lookup"><span data-stu-id="c78e9-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="c78e9-105">Для таблицы, сравнение side-by-side [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] типы данных в разделе [типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="c78e9-105">For a table showing a side-by-side comparison of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="c78e9-106">Логический тип</span><span class="sxs-lookup"><span data-stu-id="c78e9-106">Boolean Type</span></span>  
 <span data-ttu-id="c78e9-107">[Тип данных Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) значение без знака, интерпретируется как `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="c78e9-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="c78e9-108">Ширина данных зависит от реализации платформы.</span><span class="sxs-lookup"><span data-stu-id="c78e9-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="c78e9-109">Если переменная может содержать только два значения состояния, такие как ИСТИНА или ЛОЖЬ, Да или нет, или Вкл/Выкл, он объявляется как `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="c78e9-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="c78e9-110">Date-тип</span><span class="sxs-lookup"><span data-stu-id="c78e9-110">Date Type</span></span>  
 <span data-ttu-id="c78e9-111">[Тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) — 64-разрядное значение, которое содержит сведения о дате и времени.</span><span class="sxs-lookup"><span data-stu-id="c78e9-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="c78e9-112">Каждое приращение представляет 100 наносекунд времени с начала (12:00 AM) 1 января 1 года по григорианскому календарю.</span><span class="sxs-lookup"><span data-stu-id="c78e9-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="c78e9-113">Если переменная может содержать значение даты и значения времени, он объявляется как `Date`.</span><span class="sxs-lookup"><span data-stu-id="c78e9-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="c78e9-114">Тип объекта</span><span class="sxs-lookup"><span data-stu-id="c78e9-114">Object Type</span></span>  
 <span data-ttu-id="c78e9-115">[Тип данных объекта](../../../../visual-basic/language-reference/data-types/object-data-type.md) является 32-разрядный адрес, который указывает на экземпляр объекта в приложении или в другом приложении.</span><span class="sxs-lookup"><span data-stu-id="c78e9-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="c78e9-116">`Object` Переменная может ссылаться на любой объект, распознаваемый приложением, или данные любого типа данных.</span><span class="sxs-lookup"><span data-stu-id="c78e9-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="c78e9-117">Это включает в себя *типы значений*, такие как `Integer`, `Boolean`, экземпляры структур и *ссылочные типы*, которые являются экземплярами объектов, созданных из классов, таких как `String` и <xref:System.Windows.Forms.Form>и экземпляры массивов.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="c78e9-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="c78e9-118">Если переменная хранит указатель на экземпляр класса, который во время компиляции неизвестно, или он может указывать на данные различных типов данных, он объявляется как `Object`.</span><span class="sxs-lookup"><span data-stu-id="c78e9-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="c78e9-119">Преимущество `Object` имеет тип данных, можно использовать его для хранения данных любого типа данных.</span><span class="sxs-lookup"><span data-stu-id="c78e9-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="c78e9-120">Недостатком являются дополнительные операции, которые занимает больше времени выполнения и снижение производительности приложения.</span><span class="sxs-lookup"><span data-stu-id="c78e9-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="c78e9-121">При использовании `Object` переменных для типов значений, то это вызовет *упаковки* и *распаковки*.</span><span class="sxs-lookup"><span data-stu-id="c78e9-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="c78e9-122">Если она используется для ссылочных типов, вызывается *позднего связывания*.</span><span class="sxs-lookup"><span data-stu-id="c78e9-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c78e9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c78e9-123">See Also</span></span>  
 <span data-ttu-id="c78e9-124">[Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="c78e9-124">[Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
<span data-ttu-id="c78e9-125"> [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="c78e9-125"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="c78e9-126"> [Числовые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="c78e9-126"> [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span></span>  
<span data-ttu-id="c78e9-127"> [Символьные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="c78e9-127"> [Character Data Types](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span></span>  
<span data-ttu-id="c78e9-128"> [Устранение неполадок типы данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="c78e9-128"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="c78e9-129"> [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span><span class="sxs-lookup"><span data-stu-id="c78e9-129"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span></span>
