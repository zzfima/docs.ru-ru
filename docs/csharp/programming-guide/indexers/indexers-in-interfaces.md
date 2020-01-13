---
title: Руководство по программированию на C#. Индексаторы в интерфейсах
ms.date: 07/20/2015
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: 4ac51589ed1680f8484fde797c045d15beed3af9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712121"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="73b16-102">Индексаторы в интерфейсах (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="73b16-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="73b16-103">Индексаторы можно объявлять для [интерфейса](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="73b16-103">Indexers can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="73b16-104">Методы доступа индексаторов интерфейса отличаются от методов доступа индексаторов [класса](../../language-reference/keywords/class.md) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="73b16-104">Accessors of interface indexers differ from the accessors of [class](../../language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
- <span data-ttu-id="73b16-105">Методы доступа интерфейса не используют модификаторы.</span><span class="sxs-lookup"><span data-stu-id="73b16-105">Interface accessors do not use modifiers.</span></span>  
  
- <span data-ttu-id="73b16-106">Метод доступа интерфейса не имеет тела.</span><span class="sxs-lookup"><span data-stu-id="73b16-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="73b16-107">Таким образом, методы доступа нужны, чтобы указать, доступен ли индексатор для чтения и записи, только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="73b16-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="73b16-108">Ниже показан пример метода доступа индексатора для интерфейса:</span><span class="sxs-lookup"><span data-stu-id="73b16-108">The following is an example of an interface indexer accessor:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#3)]  
  
 <span data-ttu-id="73b16-109">Сигнатура индексатора должна отличаться от сигнатур любых других индексаторов, объявленных в том же интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="73b16-109">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73b16-110">Пример</span><span class="sxs-lookup"><span data-stu-id="73b16-110">Example</span></span>  
 <span data-ttu-id="73b16-111">Следующий пример демонстрирует реализацию индексаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="73b16-111">The following example shows how to implement interface indexers.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#4)]  
  
 <span data-ttu-id="73b16-112">В приведенном выше примере можно использовать явную реализацию члена интерфейса с помощью полного имени члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="73b16-112">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="73b16-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="73b16-113">For example:</span></span>  
  
```csharp  
string ISomeInterface.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="73b16-114">Тем не менее полное имя требуется только в целях устранения неоднозначности, если класс реализует более одного интерфейса с одинаковой сигнатурой индексатора.</span><span class="sxs-lookup"><span data-stu-id="73b16-114">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="73b16-115">Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых имеют одинаковую сигнатуру индексатора, требуется явная реализация члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="73b16-115">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="73b16-116">Это значит, что потребуется следующее объявление индексатора:</span><span class="sxs-lookup"><span data-stu-id="73b16-116">That is, the following indexer declaration:</span></span>  
  
```csharp  
string IEmployee.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="73b16-117">реализует индексатор в интерфейсе `IEmployee`, тогда как следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="73b16-117">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```csharp  
string ICitizen.this[int index]
{   
}   
```  
  
 <span data-ttu-id="73b16-118">реализует индексатор в интерфейсе `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="73b16-118">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b16-119">См. также</span><span class="sxs-lookup"><span data-stu-id="73b16-119">See also</span></span>

- [<span data-ttu-id="73b16-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="73b16-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="73b16-121">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="73b16-121">Indexers</span></span>](./index.md)
- [<span data-ttu-id="73b16-122">Свойства</span><span class="sxs-lookup"><span data-stu-id="73b16-122">Properties</span></span>](../classes-and-structs/properties.md)
- [<span data-ttu-id="73b16-123">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="73b16-123">Interfaces</span></span>](../interfaces/index.md)
