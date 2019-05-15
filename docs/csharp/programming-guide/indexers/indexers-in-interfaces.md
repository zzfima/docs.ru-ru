---
title: Руководство по программированию на C#. Индексаторы в интерфейсах
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: f277758a10b045a6365adfe931ce95d64eb8e445
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608578"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="cb9ee-102">Индексаторы в интерфейсах (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="cb9ee-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="cb9ee-103">Индексаторы можно объявлять для [интерфейса](../../../csharp/language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="cb9ee-103">Indexers can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="cb9ee-104">Методы доступа индексаторов интерфейса отличаются от методов доступа индексаторов [класса](../../../csharp/language-reference/keywords/class.md) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cb9ee-104">Accessors of interface indexers differ from the accessors of [class](../../../csharp/language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
- <span data-ttu-id="cb9ee-105">Методы доступа интерфейса не используют модификаторы.</span><span class="sxs-lookup"><span data-stu-id="cb9ee-105">Interface accessors do not use modifiers.</span></span>  
  
- <span data-ttu-id="cb9ee-106">Метод доступа интерфейса не имеет тела.</span><span class="sxs-lookup"><span data-stu-id="cb9ee-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="cb9ee-107">Таким образом, методы доступа нужны, чтобы указать, доступен ли индексатор для чтения и записи, только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="cb9ee-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="cb9ee-108">Ниже показан пример метода доступа индексатора для интерфейса:</span><span class="sxs-lookup"><span data-stu-id="cb9ee-108">The following is an example of an interface indexer accessor:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#3)]  
  
 <span data-ttu-id="cb9ee-109">Сигнатура индексатора должна отличаться от сигнатур любых других индексаторов, объявленных в том же интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="cb9ee-109">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb9ee-110">Пример</span><span class="sxs-lookup"><span data-stu-id="cb9ee-110">Example</span></span>  
 <span data-ttu-id="cb9ee-111">Следующий пример демонстрирует реализацию индексаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cb9ee-111">The following example shows how to implement interface indexers.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#4)]  
  
 <span data-ttu-id="cb9ee-112">В приведенном выше примере можно использовать явную реализацию члена интерфейса с помощью полного имени члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cb9ee-112">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="cb9ee-113">Например:</span><span class="sxs-lookup"><span data-stu-id="cb9ee-113">For example:</span></span>  
  
```  
string ISomeInterface.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="cb9ee-114">Тем не менее полное имя требуется только в целях устранения неоднозначности, если класс реализует более одного интерфейса с одинаковой сигнатурой индексатора.</span><span class="sxs-lookup"><span data-stu-id="cb9ee-114">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="cb9ee-115">Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых имеют одинаковую сигнатуру индексатора, требуется явная реализация члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cb9ee-115">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="cb9ee-116">Это значит, что потребуется следующее объявление индексатора:</span><span class="sxs-lookup"><span data-stu-id="cb9ee-116">That is, the following indexer declaration:</span></span>  
  
```  
string IEmployee.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="cb9ee-117">реализует индексатор в интерфейсе `IEmployee`, тогда как следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="cb9ee-117">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```  
string ICitizen.this[int index]
{   
}   
```  
  
 <span data-ttu-id="cb9ee-118">реализует индексатор в интерфейсе `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="cb9ee-118">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb9ee-119">См. также</span><span class="sxs-lookup"><span data-stu-id="cb9ee-119">See also</span></span>

- [<span data-ttu-id="cb9ee-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="cb9ee-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="cb9ee-121">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="cb9ee-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)
- [<span data-ttu-id="cb9ee-122">Свойства</span><span class="sxs-lookup"><span data-stu-id="cb9ee-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [<span data-ttu-id="cb9ee-123">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="cb9ee-123">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
