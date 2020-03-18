---
title: Руководство по программированию на C#. Индексаторы в интерфейсах
ms.date: 02/08/2020
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: 667a4213626ee37bfc5bf8c4fe78c2cf7186a73e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77627842"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="b3b1c-102">Индексаторы в интерфейсах (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="b3b1c-102">Indexers in Interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="b3b1c-103">Индексаторы можно объявлять для [интерфейса](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="b3b1c-103">Indexers can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="b3b1c-104">Методы доступа индексаторов интерфейса отличаются от методов доступа индексаторов [класса](../../language-reference/keywords/class.md) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b3b1c-104">Accessors of interface indexers differ from the accessors of [class](../../language-reference/keywords/class.md) indexers in the following ways:</span></span>

- <span data-ttu-id="b3b1c-105">Методы доступа интерфейса не используют модификаторы.</span><span class="sxs-lookup"><span data-stu-id="b3b1c-105">Interface accessors do not use modifiers.</span></span>
- <span data-ttu-id="b3b1c-106">Метод доступа интерфейса обычно не имеет тела.</span><span class="sxs-lookup"><span data-stu-id="b3b1c-106">An interface accessor typically does not have a body.</span></span>

<span data-ttu-id="b3b1c-107">Методы доступа нужны, чтобы указать, доступен ли индексатор для чтения и записи, только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="b3b1c-107">The purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span> <span data-ttu-id="b3b1c-108">Вы можете предоставить реализацию для индексатора, определенного в интерфейсе, но это случается редко.</span><span class="sxs-lookup"><span data-stu-id="b3b1c-108">You may provide an implementation for an indexer defined in an interface, but this is rare.</span></span> <span data-ttu-id="b3b1c-109">Индексаторы обычно определяют API для доступа к полям данных, а поля данных не могут быть определены в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="b3b1c-109">Indexers typically define an API to access data fields, and data fields cannot be defined in an interface.</span></span>

<span data-ttu-id="b3b1c-110">Ниже показан пример метода доступа индексатора для интерфейса:</span><span class="sxs-lookup"><span data-stu-id="b3b1c-110">The following is an example of an interface indexer accessor:</span></span>

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#DefineIndexer)]

<span data-ttu-id="b3b1c-111">Сигнатура индексатора должна отличаться от сигнатур любых других индексаторов, объявленных в том же интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="b3b1c-111">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>

## <a name="example"></a><span data-ttu-id="b3b1c-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b3b1c-112">Example</span></span>

<span data-ttu-id="b3b1c-113">Следующий пример демонстрирует реализацию индексаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b3b1c-113">The following example shows how to implement interface indexers.</span></span>

[!code-csharp[Implement](~/samples/snippets/csharp/interfaces/indexers.cs#ImplementInterface)]

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#ExampleCode)]

<span data-ttu-id="b3b1c-114">В приведенном выше примере можно использовать явную реализацию члена интерфейса с помощью полного имени члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b3b1c-114">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="b3b1c-115">Пример</span><span class="sxs-lookup"><span data-stu-id="b3b1c-115">For example</span></span>

```csharp
string IIndexInterface.this[int index]
{
}
```

<span data-ttu-id="b3b1c-116">Тем не менее полное имя требуется только в целях устранения неоднозначности, если класс реализует более одного интерфейса с одинаковой сигнатурой индексатора.</span><span class="sxs-lookup"><span data-stu-id="b3b1c-116">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="b3b1c-117">Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых имеют одинаковую сигнатуру индексатора, требуется явная реализация члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b3b1c-117">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="b3b1c-118">Это значит, что потребуется следующее объявление индексатора:</span><span class="sxs-lookup"><span data-stu-id="b3b1c-118">That is, the following indexer declaration:</span></span>

```csharp
string IEmployee.this[int index]
{
}
``

implements the indexer on the `IEmployee` interface, while the following declaration:

```csharp
string ICitizen.this[int index]
{
}
```

<span data-ttu-id="b3b1c-119">реализует индексатор в интерфейсе `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="b3b1c-119">implements the indexer on the `ICitizen` interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3b1c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b3b1c-120">See also</span></span>

- [<span data-ttu-id="b3b1c-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b3b1c-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b3b1c-122">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="b3b1c-122">Indexers</span></span>](./index.md)
- [<span data-ttu-id="b3b1c-123">Свойства</span><span class="sxs-lookup"><span data-stu-id="b3b1c-123">Properties</span></span>](../classes-and-structs/properties.md)
- [<span data-ttu-id="b3b1c-124">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="b3b1c-124">Interfaces</span></span>](../interfaces/index.md)
