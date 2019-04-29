---
title: Разработка структур
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
author: KrzysztofCwalina
ms.openlocfilehash: cc5b8d7effda31b0236477b217bccf5cf2137f8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650145"
---
# <a name="struct-design"></a><span data-ttu-id="e7f07-102">Разработка структур</span><span class="sxs-lookup"><span data-stu-id="e7f07-102">Struct Design</span></span>
<span data-ttu-id="e7f07-103">Тип общего назначения значения наиболее часто называется структурой, ключевое слово C#.</span><span class="sxs-lookup"><span data-stu-id="e7f07-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="e7f07-104">Этот раздел содержит рекомендации для проектирования общей структуры.</span><span class="sxs-lookup"><span data-stu-id="e7f07-104">This section provides guidelines for general struct design.</span></span>  
  
 <span data-ttu-id="e7f07-105">**X DO NOT** предоставляет конструктор по умолчанию для структуры.</span><span class="sxs-lookup"><span data-stu-id="e7f07-105">**X DO NOT** provide a default constructor for a struct.</span></span>  
  
 <span data-ttu-id="e7f07-106">Следование этой рекомендации обеспечивает массивы структур создаваться без необходимости запуска в конструктор для каждого элемента массива.</span><span class="sxs-lookup"><span data-stu-id="e7f07-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="e7f07-107">Обратите внимание на то, что C# не позволяет структуры могут иметь конструкторы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e7f07-107">Notice that C# does not allow structs to have default constructors.</span></span>  
  
 <span data-ttu-id="e7f07-108">**X DO NOT** определение изменяемого значения типов.</span><span class="sxs-lookup"><span data-stu-id="e7f07-108">**X DO NOT** define mutable value types.</span></span>  
  
 <span data-ttu-id="e7f07-109">Типы изменяемого значения имеют несколько проблем.</span><span class="sxs-lookup"><span data-stu-id="e7f07-109">Mutable value types have several problems.</span></span> <span data-ttu-id="e7f07-110">Например при возврате метода считывания свойства типом значения вызывающий объект получит копию.</span><span class="sxs-lookup"><span data-stu-id="e7f07-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="e7f07-111">Так как копия создается неявно, разработчики могут оказаться виду, что они изменения, копирования, а не исходное значение.</span><span class="sxs-lookup"><span data-stu-id="e7f07-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="e7f07-112">Кроме того некоторые языки (динамических языков, в частности) имеют проблемы, с помощью типов изменяемого значения, так как локальные переменные, даже при разыменовании, вызвать копирования должна быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="e7f07-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>  
  
 <span data-ttu-id="e7f07-113">**✓ DO** убедитесь, что состояние, где все экземпляров данных устанавливается равным нулю, false или null (при необходимости) является допустимым.</span><span class="sxs-lookup"><span data-stu-id="e7f07-113">**✓ DO** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>  
  
 <span data-ttu-id="e7f07-114">Это предотвращает случайное Создание недопустимые экземпляры, когда создается массив структур.</span><span class="sxs-lookup"><span data-stu-id="e7f07-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>  
  
 <span data-ttu-id="e7f07-115">**✓ DO** реализовать <xref:System.IEquatable%601> для типов значений.</span><span class="sxs-lookup"><span data-stu-id="e7f07-115">**✓ DO** implement <xref:System.IEquatable%601> on value types.</span></span>  
  
 <span data-ttu-id="e7f07-116"><xref:System.Object.Equals%2A?displayProperty=nameWithType> Упаковки-преобразования вызывает метод для типов значений, и его реализация по умолчанию не очень эффективен, поскольку он использует отражение.</span><span class="sxs-lookup"><span data-stu-id="e7f07-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="e7f07-117"><xref:System.IEquatable%601.Equals%2A> может иметь более высокую производительность и может быть реализован таким образом, чтобы упаковка-преобразование не будет.</span><span class="sxs-lookup"><span data-stu-id="e7f07-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>  
  
 <span data-ttu-id="e7f07-118">**X DO NOT** явным образом увеличить <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="e7f07-118">**X DO NOT** explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="e7f07-119">На самом деле большинство языков избежать этого.</span><span class="sxs-lookup"><span data-stu-id="e7f07-119">In fact, most languages prevent this.</span></span>  
  
 <span data-ttu-id="e7f07-120">В общем случае структуры может быть очень полезно, но должен использоваться только для небольших, единый неизменяемые значения, которые не будут упаковываться часто.</span><span class="sxs-lookup"><span data-stu-id="e7f07-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>  
  
 <span data-ttu-id="e7f07-121">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="e7f07-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e7f07-122">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e7f07-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7f07-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e7f07-123">See also</span></span>

- [<span data-ttu-id="e7f07-124">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="e7f07-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="e7f07-125">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="e7f07-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="e7f07-126">Выбор между классом и структурой</span><span class="sxs-lookup"><span data-stu-id="e7f07-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
