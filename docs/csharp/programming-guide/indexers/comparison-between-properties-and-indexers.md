---
title: Сравнение свойств и индексаторов (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 3a78b97f2cac1f2c49be03bc351d9b6f4b6438e6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861446"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="6bbfa-102">Сравнение свойств и индексаторов (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="6bbfa-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="6bbfa-103">Индексаторы подобны свойствам.</span><span class="sxs-lookup"><span data-stu-id="6bbfa-103">Indexers are like properties.</span></span> <span data-ttu-id="6bbfa-104">К методам доступа индексаторов применяются те же правила, которые определены для методов доступа к свойствам, за исключением различий, показанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6bbfa-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="6bbfa-105">Свойство</span><span class="sxs-lookup"><span data-stu-id="6bbfa-105">Property</span></span>|<span data-ttu-id="6bbfa-106">Индексатор</span><span class="sxs-lookup"><span data-stu-id="6bbfa-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="6bbfa-107">Позволяет вызывать методы как открытые члены данных.</span><span class="sxs-lookup"><span data-stu-id="6bbfa-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="6bbfa-108">Обеспечивает доступ к элементам внутренней коллекции объекта с использованием нотации массива для самого объекта.</span><span class="sxs-lookup"><span data-stu-id="6bbfa-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="6bbfa-109">Доступ по простому имени.</span><span class="sxs-lookup"><span data-stu-id="6bbfa-109">Accessed through a simple name.</span></span>|<span data-ttu-id="6bbfa-110">Доступ посредством индекса.</span><span class="sxs-lookup"><span data-stu-id="6bbfa-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="6bbfa-111">Может быть статическим членом или членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="6bbfa-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="6bbfa-112">Должен быть членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="6bbfa-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="6bbfa-113">Метод доступа [get](../../../csharp/language-reference/keywords/get.md) свойства не имеет параметров.</span><span class="sxs-lookup"><span data-stu-id="6bbfa-113">A [get](../../../csharp/language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="6bbfa-114">Метод доступа `get` индексатора имеет тот же список формальных параметров, что и сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="6bbfa-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="6bbfa-115">Метод доступа [set](../../../csharp/language-reference/keywords/set.md) свойства содержит неявный параметр `value`.</span><span class="sxs-lookup"><span data-stu-id="6bbfa-115">A [set](../../../csharp/language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="6bbfa-116">Метод доступа `set` индексатора имеет тот же список формальных параметров, что и сам индексатор, и также должен содержать параметр [value](../../../csharp/language-reference/keywords/value.md).</span><span class="sxs-lookup"><span data-stu-id="6bbfa-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../../csharp/language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="6bbfa-117">Поддерживает сокращенный синтаксис с использованием [автоматически реализуемых свойств](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6bbfa-117">Supports shortened syntax with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="6bbfa-118">Не поддерживает сокращенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="6bbfa-118">Does not support shortened syntax.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6bbfa-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6bbfa-119">See Also</span></span>

- [<span data-ttu-id="6bbfa-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6bbfa-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6bbfa-121">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="6bbfa-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
- [<span data-ttu-id="6bbfa-122">Свойства</span><span class="sxs-lookup"><span data-stu-id="6bbfa-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
