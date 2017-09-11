---
title: "Типы (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- types [C#]
- data types [C#], type system
ms.assetid: 16b984df-f417-4e02-b1e6-4589d4a614ea
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2816a5dd86e71641198a340b3a72094dffc93bdf
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="types-c-reference"></a><span data-ttu-id="4bb24-102">Типы (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4bb24-102">Types (C# Reference)</span></span>
<span data-ttu-id="4bb24-103">Система типов C# включает в себя следующие категории:</span><span class="sxs-lookup"><span data-stu-id="4bb24-103">The C# typing system contains the following categories:</span></span>  
  
-   [<span data-ttu-id="4bb24-104">Типы значений</span><span class="sxs-lookup"><span data-stu-id="4bb24-104">Value types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
  
-   [<span data-ttu-id="4bb24-105">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="4bb24-105">Reference types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [<span data-ttu-id="4bb24-106">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="4bb24-106">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
 <span data-ttu-id="4bb24-107">Переменные с типом значения содержат данные. Переменные ссылочного типа хранят ссылки на фактические данные.</span><span class="sxs-lookup"><span data-stu-id="4bb24-107">Variables that are value types store data, and those that are reference types store references to the actual data.</span></span> <span data-ttu-id="4bb24-108">Ссылочные типы также называются объектами.</span><span class="sxs-lookup"><span data-stu-id="4bb24-108">Reference types are also referred to as objects.</span></span> <span data-ttu-id="4bb24-109">Типы указателей можно использовать только в [небезопасном](../../../csharp/language-reference/keywords/unsafe.md) режиме.</span><span class="sxs-lookup"><span data-stu-id="4bb24-109">Pointer types can be used only in [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode.</span></span>  
  
 <span data-ttu-id="4bb24-110">Типы значений можно преобразовывать в ссылочные типы и обратно с помощью [упаковки-преобразования и распаковки-преобразования](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="4bb24-110">It is possible to convert a value type to a reference type, and back again to a value type, by using [boxing and unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span> <span data-ttu-id="4bb24-111">Преобразование из ссылочного типа в тип значений возможно только для упакованного типа значения.</span><span class="sxs-lookup"><span data-stu-id="4bb24-111">With the exception of a boxed value type, you cannot convert a reference type to a value type.</span></span>  
  
 <span data-ttu-id="4bb24-112">В этом разделе также представлен тип [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="4bb24-112">This section also introduces [void](../../../csharp/language-reference/keywords/void.md).</span></span>  
  
 <span data-ttu-id="4bb24-113">Типы значений также допускают значения NULL, то есть могут хранить дополнительное состояние, не являющееся значением.</span><span class="sxs-lookup"><span data-stu-id="4bb24-113">Value types are also nullable, which means they can store an additional non-value state.</span></span> <span data-ttu-id="4bb24-114">Дополнительные сведения см. в разделе [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Типы, допускающие значение NULL).</span><span class="sxs-lookup"><span data-stu-id="4bb24-114">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb24-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4bb24-115">See Also</span></span>  
 <span data-ttu-id="4bb24-116">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4bb24-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4bb24-117">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4bb24-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4bb24-118">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4bb24-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4bb24-119">[Справочные таблицы по типам](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span><span class="sxs-lookup"><span data-stu-id="4bb24-119">[Reference Tables for Types](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span></span>  
 <span data-ttu-id="4bb24-120">[Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="4bb24-120">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 [<span data-ttu-id="4bb24-121">Типы</span><span class="sxs-lookup"><span data-stu-id="4bb24-121">Types</span></span>](../../../csharp/programming-guide/types/index.md)

