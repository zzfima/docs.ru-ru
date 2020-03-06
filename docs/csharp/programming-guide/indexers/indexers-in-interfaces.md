---
title: Руководство по программированию на C#. Индексаторы в интерфейсах
ms.date: 02/08/2020
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: 667a4213626ee37bfc5bf8c4fe78c2cf7186a73e
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627842"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="4c7ff-102">Индексаторы в интерфейсах (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="4c7ff-102">Indexers in Interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="4c7ff-103">Индексаторы можно объявлять для [интерфейса](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="4c7ff-103">Indexers can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="4c7ff-104">Методы доступа индексаторов интерфейса отличаются от методов доступа индексаторов [класса](../../language-reference/keywords/class.md) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4c7ff-104">Accessors of interface indexers differ from the accessors of [class](../../language-reference/keywords/class.md) indexers in the following ways:</span></span>

- <span data-ttu-id="4c7ff-105">Методы доступа интерфейса не используют модификаторы.</span><span class="sxs-lookup"><span data-stu-id="4c7ff-105">Interface accessors do not use modifiers.</span></span>
- <span data-ttu-id="4c7ff-106">Метод доступа интерфейса обычно не имеет тела.</span><span class="sxs-lookup"><span data-stu-id="4c7ff-106">An interface accessor typically does not have a body.</span></span>

<span data-ttu-id="4c7ff-107">Методы доступа нужны, чтобы указать, доступен ли индексатор для чтения и записи, только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="4c7ff-107">The purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span> <span data-ttu-id="4c7ff-108">Вы можете предоставить реализацию для индексатора, определенного в интерфейсе, но это случается редко.</span><span class="sxs-lookup"><span data-stu-id="4c7ff-108">You may provide an implementation for an indexer defined in an interface, but this is rare.</span></span> <span data-ttu-id="4c7ff-109">Индексаторы обычно определяют API для доступа к полям данных, а поля данных не могут быть определены в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="4c7ff-109">Indexers typically define an API to access data fields, and data fields cannot be defined in an interface.</span></span>

<span data-ttu-id="4c7ff-110">Ниже показан пример метода доступа индексатора для интерфейса:</span><span class="sxs-lookup"><span data-stu-id="4c7ff-110">The following is an example of an interface indexer accessor:</span></span>

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#DefineIndexer)]

<span data-ttu-id="4c7ff-111">Сигнатура индексатора должна отличаться от сигнатур любых других индексаторов, объявленных в том же интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="4c7ff-111">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>

## <a name="example"></a><span data-ttu-id="4c7ff-112">Пример</span><span class="sxs-lookup"><span data-stu-id="4c7ff-112">Example</span></span>

<span data-ttu-id="4c7ff-113">Следующий пример демонстрирует реализацию индексаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4c7ff-113">The following example shows how to implement interface indexers.</span></span>

[!code-csharp[Implement](~/samples/snippets/csharp/interfaces/indexers.cs#ImplementInterface)]

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#ExampleCode)]

<span data-ttu-id="4c7ff-114">В приведенном выше примере можно использовать явную реализацию члена интерфейса с помощью полного имени члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4c7ff-114">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="4c7ff-115">Пример</span><span class="sxs-lookup"><span data-stu-id="4c7ff-115">For example</span></span>

```csharp
string IIndexInterface.this[int index]
{
}
```

<span data-ttu-id="4c7ff-116">Тем не менее полное имя требуется только в целях устранения неоднозначности, если класс реализует более одного интерфейса с одинаковой сигнатурой индексатора.</span><span class="sxs-lookup"><span data-stu-id="4c7ff-116">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="4c7ff-117">Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых имеют одинаковую сигнатуру индексатора, требуется явная реализация члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4c7ff-117">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="4c7ff-118">Это значит, что потребуется следующее объявление индексатора:</span><span class="sxs-lookup"><span data-stu-id="4c7ff-118">That is, the following indexer declaration:</span></span>

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

<span data-ttu-id="4c7ff-119">реализует индексатор в интерфейсе `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="4c7ff-119">implements the indexer on the `ICitizen` interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c7ff-120">См. также</span><span class="sxs-lookup"><span data-stu-id="4c7ff-120">See also</span></span>

- [<span data-ttu-id="4c7ff-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4c7ff-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4c7ff-122">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="4c7ff-122">Indexers</span></span>](./index.md)
- [<span data-ttu-id="4c7ff-123">Свойства</span><span class="sxs-lookup"><span data-stu-id="4c7ff-123">Properties</span></span>](../classes-and-structs/properties.md)
- [<span data-ttu-id="4c7ff-124">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="4c7ff-124">Interfaces</span></span>](../interfaces/index.md)
