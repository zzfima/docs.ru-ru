---
title: "Сравнение свойств и индексаторов (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
caps.latest.revision: 14
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
ms.openlocfilehash: 4bb2de1cfdcf4a8a7c847dfabe8d69124a4adf90
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="9c45d-102">Сравнение свойств и индексаторов (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="9c45d-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="9c45d-103">Индексаторы подобны свойствам.</span><span class="sxs-lookup"><span data-stu-id="9c45d-103">Indexers are like properties.</span></span> <span data-ttu-id="9c45d-104">К методам доступа индексаторов применяются те же правила, которые определены для методов доступа к свойствам, за исключением различий, показанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9c45d-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="9c45d-105">Свойство</span><span class="sxs-lookup"><span data-stu-id="9c45d-105">Property</span></span>|<span data-ttu-id="9c45d-106">Индексатор</span><span class="sxs-lookup"><span data-stu-id="9c45d-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="9c45d-107">Позволяет вызывать методы как открытые члены данных.</span><span class="sxs-lookup"><span data-stu-id="9c45d-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="9c45d-108">Обеспечивает доступ к элементам внутренней коллекции объекта с использованием нотации массива для самого объекта.</span><span class="sxs-lookup"><span data-stu-id="9c45d-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="9c45d-109">Доступ по простому имени.</span><span class="sxs-lookup"><span data-stu-id="9c45d-109">Accessed through a simple name.</span></span>|<span data-ttu-id="9c45d-110">Доступ посредством индекса.</span><span class="sxs-lookup"><span data-stu-id="9c45d-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="9c45d-111">Может быть статическим членом или членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9c45d-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="9c45d-112">Должен быть членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9c45d-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="9c45d-113">Метод доступа [get](../../../csharp/language-reference/keywords/get.md) свойства не имеет параметров.</span><span class="sxs-lookup"><span data-stu-id="9c45d-113">A [get](../../../csharp/language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="9c45d-114">Метод доступа `get` индексатора имеет тот же список формальных параметров, что и сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="9c45d-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="9c45d-115">Метод доступа [set](../../../csharp/language-reference/keywords/set.md) свойства содержит неявный параметр `value`.</span><span class="sxs-lookup"><span data-stu-id="9c45d-115">A [set](../../../csharp/language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="9c45d-116">Метод доступа `set` индексатора имеет тот же список формальных параметров, что и сам индексатор, и также должен содержать параметр [value](../../../csharp/language-reference/keywords/value.md).</span><span class="sxs-lookup"><span data-stu-id="9c45d-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../../csharp/language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="9c45d-117">Поддерживает сокращенный синтаксис с использованием [автоматически реализуемых свойств](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9c45d-117">Supports shortened syntax with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="9c45d-118">Не поддерживает сокращенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="9c45d-118">Does not support shortened syntax.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c45d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9c45d-119">See Also</span></span>  
 <span data-ttu-id="9c45d-120">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9c45d-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9c45d-121">[Индексаторы](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="9c45d-121">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 [<span data-ttu-id="9c45d-122">Свойства</span><span class="sxs-lookup"><span data-stu-id="9c45d-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

