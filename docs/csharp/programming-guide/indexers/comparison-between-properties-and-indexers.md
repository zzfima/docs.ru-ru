---
title: Руководство по программированию на C#. Сравнение свойств и индексаторов
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 41b27905edb8a0e00a6af5a4cce38988161326d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537729"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="9e17f-102">Сравнение свойств и индексаторов (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="9e17f-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="9e17f-103">Индексаторы подобны свойствам.</span><span class="sxs-lookup"><span data-stu-id="9e17f-103">Indexers are like properties.</span></span> <span data-ttu-id="9e17f-104">К методам доступа индексаторов применяются те же правила, которые определены для методов доступа к свойствам, за исключением различий, показанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9e17f-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="9e17f-105">Свойство.</span><span class="sxs-lookup"><span data-stu-id="9e17f-105">Property</span></span>|<span data-ttu-id="9e17f-106">Индексатор</span><span class="sxs-lookup"><span data-stu-id="9e17f-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="9e17f-107">Позволяет вызывать методы как открытые члены данных.</span><span class="sxs-lookup"><span data-stu-id="9e17f-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="9e17f-108">Обеспечивает доступ к элементам внутренней коллекции объекта с использованием нотации массива для самого объекта.</span><span class="sxs-lookup"><span data-stu-id="9e17f-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="9e17f-109">Доступ по простому имени.</span><span class="sxs-lookup"><span data-stu-id="9e17f-109">Accessed through a simple name.</span></span>|<span data-ttu-id="9e17f-110">Доступ посредством индекса.</span><span class="sxs-lookup"><span data-stu-id="9e17f-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="9e17f-111">Может быть статическим членом или членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9e17f-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="9e17f-112">Должен быть членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9e17f-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="9e17f-113">Метод доступа [get](../../../csharp/language-reference/keywords/get.md) свойства не имеет параметров.</span><span class="sxs-lookup"><span data-stu-id="9e17f-113">A [get](../../../csharp/language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="9e17f-114">Метод доступа `get` индексатора имеет тот же список формальных параметров, что и сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="9e17f-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="9e17f-115">Метод доступа [set](../../../csharp/language-reference/keywords/set.md) свойства содержит неявный параметр `value`.</span><span class="sxs-lookup"><span data-stu-id="9e17f-115">A [set](../../../csharp/language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="9e17f-116">Метод доступа `set` индексатора имеет тот же список формальных параметров, что и сам индексатор, и также должен содержать параметр [value](../../../csharp/language-reference/keywords/value.md).</span><span class="sxs-lookup"><span data-stu-id="9e17f-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../../csharp/language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="9e17f-117">Поддерживает сокращенный синтаксис с использованием [автоматически реализуемых свойств](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9e17f-117">Supports shortened syntax with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="9e17f-118">Не поддерживает сокращенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="9e17f-118">Does not support shortened syntax.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e17f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9e17f-119">See also</span></span>

- [<span data-ttu-id="9e17f-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9e17f-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9e17f-121">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="9e17f-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)
- [<span data-ttu-id="9e17f-122">Свойства</span><span class="sxs-lookup"><span data-stu-id="9e17f-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
