---
title: "Интерфейсы в C#. Краткий обзор языка C#"
description: "Интерфейсы определяют контракты, которые реализуются в типах C#"
keywords: ".NET, c#, интерфейсы, множественное наследование, полиморфизм"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a9bf82f4-efd1-4216-bd34-4ef0fa48c968
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 673ac56f3f5732fcda02d313b6f4273708ae365f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="interfaces"></a><span data-ttu-id="e5065-104">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="e5065-104">Interfaces</span></span>

<span data-ttu-id="e5065-105">***Интерфейс*** определяет контракт, который может быть реализован классами и структурами.</span><span class="sxs-lookup"><span data-stu-id="e5065-105">An ***interface*** defines a contract that can be implemented by classes and structs.</span></span> <span data-ttu-id="e5065-106">Интерфейс может содержать методы, свойства, события и индексаторы.</span><span class="sxs-lookup"><span data-stu-id="e5065-106">An interface can contain methods, properties, events, and indexers.</span></span> <span data-ttu-id="e5065-107">Интерфейс не предоставляет реализацию членов, которые в нем определены. Он лишь перечисляет члены, которые должны быть определены в классах или структурах, реализующих этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e5065-107">An interface does not provide implementations of the members it defines—it merely specifies the members that must be supplied by classes or structs that implement the interface.</span></span>

<span data-ttu-id="e5065-108">Интерфейсы могут применять ***множественное наследование***.</span><span class="sxs-lookup"><span data-stu-id="e5065-108">Interfaces may employ ***multiple inheritance***.</span></span> <span data-ttu-id="e5065-109">В следующем примере интерфейс `IComboBox` наследует одновременно от `ITextBox` и `IListBox`.</span><span class="sxs-lookup"><span data-stu-id="e5065-109">In the following example, the interface `IComboBox` inherits from both `ITextBox` and `IListBox`.</span></span>

<span data-ttu-id="e5065-110">[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]</span><span class="sxs-lookup"><span data-stu-id="e5065-110">[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]</span></span>

<span data-ttu-id="e5065-111">Классы и структуры могут реализовывать несколько интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="e5065-111">Classes and structs can implement multiple interfaces.</span></span> <span data-ttu-id="e5065-112">В следующем примере класс `EditBox` реализует одновременно `IControl` и `IDataBound`.</span><span class="sxs-lookup"><span data-stu-id="e5065-112">In the following example, the class `EditBox` implements both `IControl` and `IDataBound`.</span></span>

<span data-ttu-id="e5065-113">[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]</span><span class="sxs-lookup"><span data-stu-id="e5065-113">[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]</span></span>

<span data-ttu-id="e5065-114">Если класс или структура реализует конкретный интерфейс, любой экземпляр этого класса или структуры можно неявно преобразовать в такой тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e5065-114">When a class or struct implements a particular interface, instances of that class or struct can be implicitly converted to that interface type.</span></span> <span data-ttu-id="e5065-115">Пример</span><span class="sxs-lookup"><span data-stu-id="e5065-115">For example</span></span>

<span data-ttu-id="e5065-116">[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]</span><span class="sxs-lookup"><span data-stu-id="e5065-116">[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]</span></span>

<span data-ttu-id="e5065-117">Если в статическом контексте невозможно достоверно знать, что экземпляр реализует определенный интерфейс, можно использовать динамическое приведение типов.</span><span class="sxs-lookup"><span data-stu-id="e5065-117">In cases where an instance is not statically known to implement a particular interface, dynamic type casts can be used.</span></span> <span data-ttu-id="e5065-118">Например, следующие операторы используют динамическое приведение типов для получения реализации интерфейсов `IControl` и `IDataBound` для объекта.</span><span class="sxs-lookup"><span data-stu-id="e5065-118">For example, the following statements use dynamic type casts to obtain an object’s `IControl` and `IDataBound` interface implementations.</span></span> <span data-ttu-id="e5065-119">Приведения выполняются успешно, поскольку во время выполнения объект имеет фактический тип `EditBox`.</span><span class="sxs-lookup"><span data-stu-id="e5065-119">Because the run-time actual type of the object is `EditBox`, the casts succeed.</span></span>

<span data-ttu-id="e5065-120">[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]</span><span class="sxs-lookup"><span data-stu-id="e5065-120">[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]</span></span>

<span data-ttu-id="e5065-121">В предыдущем примере для класса `EditBox` метод `Paint` из интерфейса `IControl` и метод `Bind` из интерфейса `IDataBound` реализуются с помощью открытых членов.</span><span class="sxs-lookup"><span data-stu-id="e5065-121">In the previous `EditBox` class, the `Paint` method from the `IControl` interface and the `Bind` method from the `IDataBound` interface are implemented using public members.</span></span> <span data-ttu-id="e5065-122">C# также поддерживает явные ***реализации членов интерфейса***, что позволяет классам и структурам не использовать открытые члены.</span><span class="sxs-lookup"><span data-stu-id="e5065-122">C# also supports explicit ***interface member implementations***, enabling the class or struct to avoid making the members public.</span></span> <span data-ttu-id="e5065-123">Явная реализация члена интерфейса записывается с использованием полного имени члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e5065-123">An explicit interface member implementation is written using the fully qualified interface member name.</span></span> <span data-ttu-id="e5065-124">Например, класс `EditBox` может реализовывать методы `IControl.Paint` и `IDataBound.Bind` с использованием явной реализации членов интерфейса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e5065-124">For example, the `EditBox` class could implement the `IControl.Paint` and `IDataBound.Bind` methods using explicit interface member implementations as follows.</span></span>

<span data-ttu-id="e5065-125">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]</span><span class="sxs-lookup"><span data-stu-id="e5065-125">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]</span></span>

<span data-ttu-id="e5065-126">Обращение к явным членам интерфейса можно осуществлять только через тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e5065-126">Explicit interface members can only be accessed via the interface type.</span></span> <span data-ttu-id="e5065-127">Например, реализация `IControl.Paint`, представленная в предыдущем примере класса EditBox, может вызываться только с предварительным преобразованием ссылки `EditBox` к типу интерфейса `IControl`.</span><span class="sxs-lookup"><span data-stu-id="e5065-127">For example, the implementation of `IControl.Paint` provided by the previous EditBox class can only be invoked by first converting the `EditBox` reference to the `IControl` interface type.</span></span>

<span data-ttu-id="e5065-128">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]</span><span class="sxs-lookup"><span data-stu-id="e5065-128">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e5065-129">[Назад](arrays.md)
[Вперед](enums.md)</span><span class="sxs-lookup"><span data-stu-id="e5065-129">[Previous](arrays.md)
[Next](enums.md)</span></span>

