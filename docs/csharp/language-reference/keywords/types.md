---
title: Типы (Справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- types [C#]
- data types [C#], type system
ms.assetid: 16b984df-f417-4e02-b1e6-4589d4a614ea
ms.openlocfilehash: c5c29f5d9a1a4e25e2d5f8816a0df31fa9a91fb1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506325"
---
# <a name="types-c-reference"></a><span data-ttu-id="bda18-102">Типы (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="bda18-102">Types (C# Reference)</span></span>
<span data-ttu-id="bda18-103">Система типов C# включает в себя следующие категории:</span><span class="sxs-lookup"><span data-stu-id="bda18-103">The C# typing system contains the following categories:</span></span>  
  
-   [<span data-ttu-id="bda18-104">Типы значений</span><span class="sxs-lookup"><span data-stu-id="bda18-104">Value types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
  
-   [<span data-ttu-id="bda18-105">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="bda18-105">Reference types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [<span data-ttu-id="bda18-106">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="bda18-106">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
 <span data-ttu-id="bda18-107">Переменные с типом значения содержат данные. Переменные ссылочного типа хранят ссылки на фактические данные.</span><span class="sxs-lookup"><span data-stu-id="bda18-107">Variables that are value types store data, and those that are reference types store references to the actual data.</span></span> <span data-ttu-id="bda18-108">Ссылочные типы также называются объектами.</span><span class="sxs-lookup"><span data-stu-id="bda18-108">Reference types are also referred to as objects.</span></span> <span data-ttu-id="bda18-109">Типы указателей можно использовать только в [небезопасном](../../../csharp/language-reference/keywords/unsafe.md) режиме.</span><span class="sxs-lookup"><span data-stu-id="bda18-109">Pointer types can be used only in [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode.</span></span>  
  
 <span data-ttu-id="bda18-110">Типы значений можно преобразовывать в ссылочные типы и обратно с помощью [упаковки-преобразования и распаковки-преобразования](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="bda18-110">It is possible to convert a value type to a reference type, and back again to a value type, by using [boxing and unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span> <span data-ttu-id="bda18-111">Преобразование из ссылочного типа в тип значений возможно только для упакованного типа значения.</span><span class="sxs-lookup"><span data-stu-id="bda18-111">With the exception of a boxed value type, you cannot convert a reference type to a value type.</span></span>  
  
 <span data-ttu-id="bda18-112">В этом разделе также представлен тип [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="bda18-112">This section also introduces [void](../../../csharp/language-reference/keywords/void.md).</span></span>  
  
 <span data-ttu-id="bda18-113">Типы значений также допускают значения NULL, то есть могут хранить дополнительное состояние, не являющееся значением.</span><span class="sxs-lookup"><span data-stu-id="bda18-113">Value types are also nullable, which means they can store an additional non-value state.</span></span> <span data-ttu-id="bda18-114">Дополнительные сведения см. в разделе [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Типы, допускающие значение NULL).</span><span class="sxs-lookup"><span data-stu-id="bda18-114">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda18-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bda18-115">See Also</span></span>

- [<span data-ttu-id="bda18-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="bda18-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="bda18-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bda18-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="bda18-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="bda18-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="bda18-119">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="bda18-119">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
- [<span data-ttu-id="bda18-120">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="bda18-120">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
- [<span data-ttu-id="bda18-121">Типы</span><span class="sxs-lookup"><span data-stu-id="bda18-121">Types</span></span>](../../../csharp/programming-guide/types/index.md)
