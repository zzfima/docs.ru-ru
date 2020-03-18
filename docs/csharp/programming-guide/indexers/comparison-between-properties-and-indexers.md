---
title: Руководство по программированию на C#. Сравнение свойств и индексаторов
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 330d222083ce599719698c023803196dfe88da84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712134"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="a3efe-102">Сравнение свойств и индексаторов (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="a3efe-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="a3efe-103">Индексаторы подобны свойствам.</span><span class="sxs-lookup"><span data-stu-id="a3efe-103">Indexers are like properties.</span></span> <span data-ttu-id="a3efe-104">К методам доступа индексаторов применяются те же правила, которые определены для методов доступа к свойствам, за исключением различий, показанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a3efe-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="a3efe-105">Свойство</span><span class="sxs-lookup"><span data-stu-id="a3efe-105">Property</span></span>|<span data-ttu-id="a3efe-106">Индексатор</span><span class="sxs-lookup"><span data-stu-id="a3efe-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="a3efe-107">Позволяет вызывать методы как открытые члены данных.</span><span class="sxs-lookup"><span data-stu-id="a3efe-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="a3efe-108">Обеспечивает доступ к элементам внутренней коллекции объекта с использованием нотации массива для самого объекта.</span><span class="sxs-lookup"><span data-stu-id="a3efe-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="a3efe-109">Доступ по простому имени.</span><span class="sxs-lookup"><span data-stu-id="a3efe-109">Accessed through a simple name.</span></span>|<span data-ttu-id="a3efe-110">Доступ посредством индекса.</span><span class="sxs-lookup"><span data-stu-id="a3efe-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="a3efe-111">Может быть статическим членом или членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a3efe-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="a3efe-112">Должен быть членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a3efe-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="a3efe-113">Метод доступа [get](../../language-reference/keywords/get.md) свойства не имеет параметров.</span><span class="sxs-lookup"><span data-stu-id="a3efe-113">A [get](../../language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="a3efe-114">Метод доступа `get` индексатора имеет тот же список формальных параметров, что и сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="a3efe-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="a3efe-115">Метод доступа [set](../../language-reference/keywords/set.md) свойства содержит неявный параметр `value`.</span><span class="sxs-lookup"><span data-stu-id="a3efe-115">A [set](../../language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="a3efe-116">Метод доступа `set` индексатора имеет тот же список формальных параметров, что и сам индексатор, и также должен содержать параметр [value](../../language-reference/keywords/value.md).</span><span class="sxs-lookup"><span data-stu-id="a3efe-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="a3efe-117">Поддерживает сокращенный синтаксис с использованием [автоматически реализуемых свойств](../classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a3efe-117">Supports shortened syntax with [Auto-Implemented Properties](../classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="a3efe-118">Поддерживает элементы в виде выражения для индексаторов только для получения.</span><span class="sxs-lookup"><span data-stu-id="a3efe-118">Supports expression bodied members for get only indexers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3efe-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a3efe-119">See also</span></span>

- [<span data-ttu-id="a3efe-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a3efe-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a3efe-121">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="a3efe-121">Indexers</span></span>](./index.md)
- [<span data-ttu-id="a3efe-122">Свойства</span><span class="sxs-lookup"><span data-stu-id="a3efe-122">Properties</span></span>](../classes-and-structs/properties.md)
