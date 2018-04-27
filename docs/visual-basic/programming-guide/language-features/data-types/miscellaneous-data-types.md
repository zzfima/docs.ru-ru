---
title: Прочие типы данных (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f80aacccab4c215b3e3917cc73097080aa6b9941
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="0f117-102">Прочие типы данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f117-102">Miscellaneous Data Types (Visual Basic)</span></span>
<span data-ttu-id="0f117-103">Visual Basic предоставляет несколько типов данных, не предназначенных для чисел или символов.</span><span class="sxs-lookup"><span data-stu-id="0f117-103">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="0f117-104">Они предусмотрены для настраиваемых данных, таких как Да/нет значений, значений даты и времени и адресов объектов.</span><span class="sxs-lookup"><span data-stu-id="0f117-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="0f117-105">Таблица, показывающая сравнение типы данных Visual Basic, см. [типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="0f117-105">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="0f117-106">Логический тип</span><span class="sxs-lookup"><span data-stu-id="0f117-106">Boolean Type</span></span>  
 <span data-ttu-id="0f117-107">[Тип данных Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) имеет значение без знака, которое интерпретируется как `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="0f117-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="0f117-108">Ширина данных зависит от реализации платформы.</span><span class="sxs-lookup"><span data-stu-id="0f117-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="0f117-109">Если переменная может содержать только два значения состояния, например true или false, Да/Нет или Вкл/Выкл, объявите его как `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="0f117-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="0f117-110">Date-тип</span><span class="sxs-lookup"><span data-stu-id="0f117-110">Date Type</span></span>  
 <span data-ttu-id="0f117-111">[Тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) — 64-разрядное значение, которое содержит сведения о дате и времени.</span><span class="sxs-lookup"><span data-stu-id="0f117-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="0f117-112">Каждое приращение представляет 100 наносекунд затраченного времени с начала (12:00 AM) 1 января 1 года по григорианскому календарю.</span><span class="sxs-lookup"><span data-stu-id="0f117-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="0f117-113">Если переменная может содержать значение даты и времени значение, он объявляется как `Date`.</span><span class="sxs-lookup"><span data-stu-id="0f117-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="0f117-114">Тип объекта</span><span class="sxs-lookup"><span data-stu-id="0f117-114">Object Type</span></span>  
 <span data-ttu-id="0f117-115">[Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) является 32-разрядный адрес, который указывает на экземпляр объекта в приложении или в другом приложении.</span><span class="sxs-lookup"><span data-stu-id="0f117-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="0f117-116">`Object` Переменной может указывать на любой объект, распознаваемый приложением, а также данные любого типа данных.</span><span class="sxs-lookup"><span data-stu-id="0f117-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="0f117-117">Это включает в себя *типы значений*, такие как `Integer`, `Boolean`, экземпляры структур и *ссылочные типы*, которые являются экземплярами объектов, созданных из классов, таких как `String`и <xref:System.Windows.Forms.Form>и экземпляры массивов.</span><span class="sxs-lookup"><span data-stu-id="0f117-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="0f117-118">Если переменная хранит указатель на экземпляр класса, который вы не знаете во время компиляции, или он может указывать на данные различных типов данных, он объявляется как `Object`.</span><span class="sxs-lookup"><span data-stu-id="0f117-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="0f117-119">Преимущество `Object` имеет тип данных, его можно использовать для хранения данных любого типа данных.</span><span class="sxs-lookup"><span data-stu-id="0f117-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="0f117-120">Недостаток заключается в том, что при этом дополнительные операции, занимает больше времени выполнения и снижение производительности приложения.</span><span class="sxs-lookup"><span data-stu-id="0f117-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="0f117-121">Если вы используете `Object` переменных для типов значений, при этом *упаковка-преобразование* и *распаковки*.</span><span class="sxs-lookup"><span data-stu-id="0f117-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="0f117-122">Если вы используете для ссылочных типов, при этом *позднего связывания*.</span><span class="sxs-lookup"><span data-stu-id="0f117-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f117-123">См. также</span><span class="sxs-lookup"><span data-stu-id="0f117-123">See Also</span></span>  
 [<span data-ttu-id="0f117-124">Знаки типов</span><span class="sxs-lookup"><span data-stu-id="0f117-124">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="0f117-125">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="0f117-125">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="0f117-126">Числовые типы данных</span><span class="sxs-lookup"><span data-stu-id="0f117-126">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="0f117-127">Символьные типы данных</span><span class="sxs-lookup"><span data-stu-id="0f117-127">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [<span data-ttu-id="0f117-128">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="0f117-128">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="0f117-129">Раннее и позднее связывание</span><span class="sxs-lookup"><span data-stu-id="0f117-129">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
