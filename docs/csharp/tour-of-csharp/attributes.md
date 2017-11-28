---
title: "Атрибуты в C#. Краткий обзор языка C#"
description: "Узнайте о декларативном программировании в C# с использованием атрибутов"
keywords: .NET, C#
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 753bcfe2-7ddd-4487-9513-ba70937fc8e9
ms.openlocfilehash: 6878a408ef892ee47a03bfa04f736b9bf9671696
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2017
---
# <a name="attributes"></a><span data-ttu-id="bdf4a-104">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bdf4a-104">Attributes</span></span>

<span data-ttu-id="bdf4a-105">Типы, члены и другие сущности в программе C# поддерживают модификаторы, которые управляют некоторыми аспектами их поведения.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-105">Types, members, and other entities in a C# program support modifiers that control certain aspects of their behavior.</span></span> <span data-ttu-id="bdf4a-106">Например, доступность метода определяется с помощью модификаторов `public`, `protected`, `internal` и `private`.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-106">For example, the accessibility of a method is controlled using the `public`, `protected`, `internal`, and `private` modifiers.</span></span> <span data-ttu-id="bdf4a-107">C# обобщает эту возможность, позволяя пользователям определять собственные типы декларативных сведений, назначать их для сущностей программы и извлекать во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-107">C# generalizes this capability such that user-defined types of declarative information can be attached to program entities and retrieved at run-time.</span></span> <span data-ttu-id="bdf4a-108">В программах эти дополнительные декларативные сведения определяются и используются посредством ***атрибутов***.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-108">Programs specify this additional declarative information by defining and using ***attributes***.</span></span>

<span data-ttu-id="bdf4a-109">Следующий пример кода объявляет атрибут `HelpAttribute`, который можно поместить в сущности программы для указания связей с соответствующей документацией.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-109">The following example declares a `HelpAttribute` attribute that can be placed on program entities to provide links to their associated documentation.</span></span>

[!code-csharp[AttributeDefined](../../../samples/snippets/csharp/tour/attributes/Program.cs#L3-L20)]

<span data-ttu-id="bdf4a-110">Все классы атрибутов являются производными от базового класса <xref:System.Attribute>, который предоставляется в стандартной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-110">All attribute classes derive from the <xref:System.Attribute> base class provided by the standard library.</span></span> <span data-ttu-id="bdf4a-111">Чтобы задать атрибут, его имя и возможные аргументы указываются в квадратных скобках непосредственно перед объявлением соответствующей сущности.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-111">Attributes can be applied by giving their name, along with any arguments, inside square brackets just before the associated declaration.</span></span> <span data-ttu-id="bdf4a-112">Если имя атрибута заканчивается на `Attribute`, этот суффикс можно опускать при указании ссылки на этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-112">If an attribute’s name ends in `Attribute`, that part of the name can be omitted when the attribute is referenced.</span></span> <span data-ttu-id="bdf4a-113">Например, атрибут с именем `HelpAttribute` можно использовать так:</span><span class="sxs-lookup"><span data-stu-id="bdf4a-113">For example, the `HelpAttribute` attribute can be used as follows.</span></span>

[!code-csharp[AttributeApplied](../../../samples/snippets/csharp/tour/attributes/Program.cs#L22-L28)]

<span data-ttu-id="bdf4a-114">Этот пример кода присоединяет атрибут `HelpAttribute` к классу `Widget`.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-114">This example attaches a `HelpAttribute` to the `Widget` class.</span></span> <span data-ttu-id="bdf4a-115">Также он добавляет другой атрибут `HelpAttribute` для метода `Display` в этом классе.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-115">It adds another `HelpAttribute` to the `Display` method in the class.</span></span> <span data-ttu-id="bdf4a-116">Открытые конструкторы класса атрибута указывают, какие сведения необходимо указать при назначении атрибута некоторой сущности программы.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-116">The public constructors of an attribute class control the information that must be provided when the attribute is attached to a program entity.</span></span> <span data-ttu-id="bdf4a-117">Дополнительные сведения можно предоставить через обращения к открытым свойствам класса атрибута, доступным для чтения и записи (например, как указанная выше ссылка на свойство `Topic`).</span><span class="sxs-lookup"><span data-stu-id="bdf4a-117">Additional information can be provided by referencing public read-write properties of the attribute class (such as the reference to the `Topic` property previously).</span></span>

<span data-ttu-id="bdf4a-118">Когда выполняется запрос конкретного атрибута через отражение, вызывается конструктор для класса атрибута с указанием сведений, представленных в исходном коде программы, а затем возвращается созданный экземпляр атрибута.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-118">When a particular attribute is requested through reflection, the constructor for the attribute class is invoked with the information provided in the program source, and the resulting attribute instance is returned.</span></span> <span data-ttu-id="bdf4a-119">Если дополнительные сведения предоставляются через свойства, перед возвращением экземпляра атрибута этим свойствам присваиваются указанные значения.</span><span class="sxs-lookup"><span data-stu-id="bdf4a-119">If additional information was provided through properties, those properties are set to the given values before the attribute instance is returned.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="bdf4a-120">Назад</span><span class="sxs-lookup"><span data-stu-id="bdf4a-120">Previous</span></span>](delegates.md)
