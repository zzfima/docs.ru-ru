---
title: Справочник по C#. Типы
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- types [C#]
- data types [C#], type system
ms.assetid: 16b984df-f417-4e02-b1e6-4589d4a614ea
ms.openlocfilehash: 41406e74a207f289968017f1f9869b23b165c34b
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236665"
---
# <a name="types-c-reference"></a><span data-ttu-id="54c46-102">Типы (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="54c46-102">Types (C# Reference)</span></span>

<span data-ttu-id="54c46-103">Система типов C# включает в себя следующие категории:</span><span class="sxs-lookup"><span data-stu-id="54c46-103">The C# typing system contains the following categories:</span></span>

- [<span data-ttu-id="54c46-104">Типы значений</span><span class="sxs-lookup"><span data-stu-id="54c46-104">Value types</span></span>](value-types.md)

- [<span data-ttu-id="54c46-105">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="54c46-105">Reference types</span></span>](reference-types.md)

- [<span data-ttu-id="54c46-106">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="54c46-106">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)

 <span data-ttu-id="54c46-107">Переменные с типом значения содержат данные. Переменные ссылочного типа хранят ссылки на фактические данные.</span><span class="sxs-lookup"><span data-stu-id="54c46-107">Variables that are value types store data, and those that are reference types store references to the actual data.</span></span> <span data-ttu-id="54c46-108">Экземпляры ссылочных типов также называются объектами.</span><span class="sxs-lookup"><span data-stu-id="54c46-108">Instances of reference types are also referred to as objects.</span></span> <span data-ttu-id="54c46-109">Типы указателей можно использовать только в [небезопасном](unsafe.md) режиме.</span><span class="sxs-lookup"><span data-stu-id="54c46-109">Pointer types can be used only in [unsafe](unsafe.md) mode.</span></span>

 <span data-ttu-id="54c46-110">Типы значений можно преобразовывать в ссылочные типы и обратно с помощью [упаковки-преобразования и распаковки-преобразования](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="54c46-110">It's possible to convert a value type to a reference type, and back again to a value type, by using [boxing and unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span> <span data-ttu-id="54c46-111">Преобразование из ссылочного типа в тип значений возможно только для упакованного типа значения.</span><span class="sxs-lookup"><span data-stu-id="54c46-111">With the exception of a boxed value type, you cannot convert a reference type to a value type.</span></span>

 <span data-ttu-id="54c46-112">В этом разделе также представлен тип [void](void.md).</span><span class="sxs-lookup"><span data-stu-id="54c46-112">This section also introduces [void](void.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="54c46-113">См. также</span><span class="sxs-lookup"><span data-stu-id="54c46-113">See also</span></span>

- [<span data-ttu-id="54c46-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="54c46-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="54c46-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="54c46-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="54c46-116">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="54c46-116">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="54c46-117">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="54c46-117">Reference Tables for Types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="54c46-118">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="54c46-118">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="54c46-119">Типы</span><span class="sxs-lookup"><span data-stu-id="54c46-119">Types</span></span>](../../programming-guide/types/index.md)
