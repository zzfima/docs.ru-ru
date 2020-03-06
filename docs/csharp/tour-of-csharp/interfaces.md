---
title: Интерфейсы в C#. Краткий обзор языка C#
description: Интерфейсы определяют контракты, которые реализуются в типах C#
ms.date: 02/27/2020
ms.assetid: a9bf82f4-efd1-4216-bd34-4ef0fa48c968
ms.openlocfilehash: 62d94462fa481379cf70d63a598deb7f36be204f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159134"
---
# <a name="interfaces"></a><span data-ttu-id="039cc-103">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="039cc-103">Interfaces</span></span>

<span data-ttu-id="039cc-104">***Интерфейс*** определяет контракт, который может быть реализован классами и структурами.</span><span class="sxs-lookup"><span data-stu-id="039cc-104">An ***interface*** defines a contract that can be implemented by classes and structs.</span></span> <span data-ttu-id="039cc-105">Интерфейс может содержать методы, свойства, события и индексаторы.</span><span class="sxs-lookup"><span data-stu-id="039cc-105">An interface can contain methods, properties, events, and indexers.</span></span> <span data-ttu-id="039cc-106">Интерфейс не предоставляет реализацию членов, которые в нем определены. Он лишь перечисляет члены, которые должны быть определены в классах или структурах, реализующих этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="039cc-106">An interface doesn't provide implementations of the members it defines—it merely specifies the members that must be supplied by classes or structs that implement the interface.</span></span>

<span data-ttu-id="039cc-107">Интерфейсы могут применять ***множественное наследование***.</span><span class="sxs-lookup"><span data-stu-id="039cc-107">Interfaces may employ ***multiple inheritance***.</span></span> <span data-ttu-id="039cc-108">В следующем примере интерфейс `IComboBox` наследует одновременно от `ITextBox` и `IListBox`.</span><span class="sxs-lookup"><span data-stu-id="039cc-108">In the following example, the interface `IComboBox` inherits from both `ITextBox` and `IListBox`.</span></span>

[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]

<span data-ttu-id="039cc-109">Классы и структуры могут реализовывать несколько интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="039cc-109">Classes and structs can implement multiple interfaces.</span></span> <span data-ttu-id="039cc-110">В следующем примере класс `EditBox` реализует одновременно `IControl` и `IDataBound`.</span><span class="sxs-lookup"><span data-stu-id="039cc-110">In the following example, the class `EditBox` implements both `IControl` and `IDataBound`.</span></span>

[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]

<span data-ttu-id="039cc-111">Если класс или структура реализует конкретный интерфейс, любой экземпляр этого класса или структуры можно неявно преобразовать в такой тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="039cc-111">When a class or struct implements a particular interface, instances of that class or struct can be implicitly converted to that interface type.</span></span> <span data-ttu-id="039cc-112">Пример</span><span class="sxs-lookup"><span data-stu-id="039cc-112">For example</span></span>

[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]

<span data-ttu-id="039cc-113">Если в статическом контексте невозможно достоверно знать, что экземпляр реализует определенный интерфейс, можно использовать динамическое приведение типов.</span><span class="sxs-lookup"><span data-stu-id="039cc-113">In cases where an instance isn't statically known to implement a particular interface, dynamic type casts can be used.</span></span> <span data-ttu-id="039cc-114">Например, следующие операторы используют динамическое приведение типов для получения реализации интерфейсов `IControl` и `IDataBound` для объекта.</span><span class="sxs-lookup"><span data-stu-id="039cc-114">For example, the following statements use dynamic type casts to obtain an object’s `IControl` and `IDataBound` interface implementations.</span></span> <span data-ttu-id="039cc-115">Приведения выполняются успешно, поскольку во время выполнения объект имеет фактический тип `EditBox`.</span><span class="sxs-lookup"><span data-stu-id="039cc-115">Because the run-time actual type of the object is `EditBox`, the casts succeed.</span></span>

[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]

<span data-ttu-id="039cc-116">В предыдущем примере для класса `EditBox` метод `Paint` из интерфейса `IControl` и метод `Bind` из интерфейса `IDataBound` реализуются с помощью открытых членов.</span><span class="sxs-lookup"><span data-stu-id="039cc-116">In the previous `EditBox` class, the `Paint` method from the `IControl` interface and the `Bind` method from the `IDataBound` interface are implemented using public members.</span></span> <span data-ttu-id="039cc-117">C# также поддерживает явные ***реализации членов интерфейса***, что позволяет классам и структурам не использовать открытые члены.</span><span class="sxs-lookup"><span data-stu-id="039cc-117">C# also supports explicit ***interface member implementations***, enabling the class or struct to avoid making the members public.</span></span> <span data-ttu-id="039cc-118">Явная реализация члена интерфейса записывается с использованием полного имени члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="039cc-118">An explicit interface member implementation is written using the fully qualified interface member name.</span></span> <span data-ttu-id="039cc-119">Например, класс `EditBox` может реализовывать методы `IControl.Paint` и `IDataBound.Bind` с использованием явной реализации членов интерфейса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="039cc-119">For example, the `EditBox` class could implement the `IControl.Paint` and `IDataBound.Bind` methods using explicit interface member implementations as follows.</span></span>

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]

<span data-ttu-id="039cc-120">Обращение к явным членам интерфейса можно осуществлять только через тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="039cc-120">Explicit interface members can only be accessed via the interface type.</span></span> <span data-ttu-id="039cc-121">Например, реализация `IControl.Paint`, представленная в предыдущем примере класса EditBox, может вызываться только с предварительным преобразованием ссылки `EditBox` к типу интерфейса `IControl`.</span><span class="sxs-lookup"><span data-stu-id="039cc-121">For example, the implementation of `IControl.Paint` provided by the previous EditBox class can only be invoked by first converting the `EditBox` reference to the `IControl` interface type.</span></span>

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]

>[!div class="step-by-step"]
><span data-ttu-id="039cc-122">[Назад](arrays.md)
>[Вперед](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="039cc-122">[Previous](arrays.md)
[Next](delegates.md)</span></span>
