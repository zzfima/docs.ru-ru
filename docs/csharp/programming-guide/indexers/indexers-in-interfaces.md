---
title: "Индексаторы в интерфейсах (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
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
ms.openlocfilehash: 2715602dadea40324f613bb07b5dd332ed18c25c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="64241-102">Индексаторы в интерфейсах (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="64241-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="64241-103">Индексаторы можно объявлять для [интерфейса](../../../csharp/language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="64241-103">Indexers can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="64241-104">Методы доступа индексаторов интерфейса отличаются от методов доступа индексаторов [класса](../../../csharp/language-reference/keywords/class.md) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="64241-104">Accessors of interface indexers differ from the accessors of [class](../../../csharp/language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
-   <span data-ttu-id="64241-105">Методы доступа интерфейса не используют модификаторы.</span><span class="sxs-lookup"><span data-stu-id="64241-105">Interface accessors do not use modifiers.</span></span>  
  
-   <span data-ttu-id="64241-106">Метод доступа интерфейса не имеет тела.</span><span class="sxs-lookup"><span data-stu-id="64241-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="64241-107">Таким образом, методы доступа нужны, чтобы указать, доступен ли индексатор для чтения и записи, только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="64241-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="64241-108">Ниже показан пример метода доступа индексатора для интерфейса:</span><span class="sxs-lookup"><span data-stu-id="64241-108">The following is an example of an interface indexer accessor:</span></span>  
  
 <span data-ttu-id="64241-109">[!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="64241-109">[!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]</span></span>  
  
 <span data-ttu-id="64241-110">Сигнатура индексатора должна отличаться от сигнатур любых других индексаторов, объявленных в том же интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="64241-110">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64241-111">Пример</span><span class="sxs-lookup"><span data-stu-id="64241-111">Example</span></span>  
 <span data-ttu-id="64241-112">Следующий пример демонстрирует реализацию индексаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="64241-112">The following example shows how to implement interface indexers.</span></span>  
  
 <span data-ttu-id="64241-113">[!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="64241-113">[!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="64241-114">В приведенном выше примере можно использовать явную реализацию члена интерфейса с помощью полного имени члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="64241-114">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="64241-115">Например:</span><span class="sxs-lookup"><span data-stu-id="64241-115">For example:</span></span>  
  
```  
public string ISomeInterface.this   
{   
}   
```  
  
 <span data-ttu-id="64241-116">Тем не менее полное имя требуется только в целях устранения неоднозначности, если класс реализует более одного интерфейса с одинаковой сигнатурой индексатора.</span><span class="sxs-lookup"><span data-stu-id="64241-116">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="64241-117">Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых имеют одинаковую сигнатуру индексатора, требуется явная реализация члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="64241-117">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="64241-118">Это значит, что потребуется следующее объявление индексатора:</span><span class="sxs-lookup"><span data-stu-id="64241-118">That is, the following indexer declaration:</span></span>  
  
```  
public string IEmployee.this   
{   
}   
```  
  
 <span data-ttu-id="64241-119">реализует индексатор в интерфейсе `IEmployee`, тогда как следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="64241-119">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```  
public string ICitizen.this   
{   
}   
```  
  
 <span data-ttu-id="64241-120">реализует индексатор в интерфейсе `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="64241-120">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64241-121">См. также</span><span class="sxs-lookup"><span data-stu-id="64241-121">See Also</span></span>  
 <span data-ttu-id="64241-122">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="64241-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="64241-123">[Индексаторы](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="64241-123">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="64241-124">[Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="64241-124">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 [<span data-ttu-id="64241-125">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="64241-125">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

