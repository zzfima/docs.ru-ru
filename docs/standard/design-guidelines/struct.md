---
title: Разработка структур
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2621aa96cf89b453d5faec3357d0890ca36251d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572740"
---
# <a name="struct-design"></a><span data-ttu-id="ea1cd-102">Разработка структур</span><span class="sxs-lookup"><span data-stu-id="ea1cd-102">Struct Design</span></span>
<span data-ttu-id="ea1cd-103">Тип значения общего назначения наиболее часто называется структурой зарезервированного слова C#.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="ea1cd-104">Этот раздел содержит рекомендации по общие структуры конструктора.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-104">This section provides guidelines for general struct design.</span></span>  
  
 <span data-ttu-id="ea1cd-105">**X не** предоставляет конструктор по умолчанию для структуры.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-105">**X DO NOT** provide a default constructor for a struct.</span></span>  
  
 <span data-ttu-id="ea1cd-106">Следование этой рекомендации позволяет массивы структур создаваться без запуска конструктора для каждого элемента массива.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="ea1cd-107">Обратите внимание, что C# не позволяет структуры могут иметь конструкторы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-107">Notice that C# does not allow structs to have default constructors.</span></span>  
  
 <span data-ttu-id="ea1cd-108">**X не** определение изменяемого значения типов.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-108">**X DO NOT** define mutable value types.</span></span>  
  
 <span data-ttu-id="ea1cd-109">Изменяемое значение типы имеют ряд проблем.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-109">Mutable value types have several problems.</span></span> <span data-ttu-id="ea1cd-110">Например при возврате из метода получения свойства тип значения вызывающий объект получает копию.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="ea1cd-111">Так как копия создается неявно, разработчики может оказаться помнить, что они изменения копии, а не исходное значение.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="ea1cd-112">Кроме того некоторые языки (динамическими языками, в частности) имеют проблемы при использовании изменяемого значения типов, так как локальные переменные, даже при разыменовании, привести копирования должна быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>  
  
 <span data-ttu-id="ea1cd-113">**✓ СДЕЛАТЬ** убедитесь, что состояние, где все экземпляров данных устанавливается равным нулю, false или null (при необходимости) является допустимым.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-113">**✓ DO** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>  
  
 <span data-ttu-id="ea1cd-114">Это предотвращает случайное Создание недопустимые экземпляры, когда создается массив структур.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>  
  
 <span data-ttu-id="ea1cd-115">**СДЕЛАТЬ ✓** реализовать <xref:System.IEquatable%601> для типов значений.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-115">**✓ DO** implement <xref:System.IEquatable%601> on value types.</span></span>  
  
 <span data-ttu-id="ea1cd-116"><xref:System.Object.Equals%2A?displayProperty=nameWithType> Упаковка-преобразование вызывает метод для типов значений, и его реализация по умолчанию не очень эффективна, так как он использует отражение.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="ea1cd-117"><xref:System.IEquatable%601.Equals%2A> может быть гораздо более высокую производительность и может быть реализовано так, чтобы упаковка-преобразование не будет.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>  
  
 <span data-ttu-id="ea1cd-118">**X не** явным образом увеличить <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-118">**X DO NOT** explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="ea1cd-119">На самом деле большинство языков отключены.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-119">In fact, most languages prevent this.</span></span>  
  
 <span data-ttu-id="ea1cd-120">В общем случае структуры может быть очень полезно, но можно использовать только для небольших, один постоянные значения, которые не должен быть упакован часто.</span><span class="sxs-lookup"><span data-stu-id="ea1cd-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>  
  
 <span data-ttu-id="ea1cd-121">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="ea1cd-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ea1cd-122">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="ea1cd-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea1cd-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ea1cd-123">See Also</span></span>  
 [<span data-ttu-id="ea1cd-124">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="ea1cd-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="ea1cd-125">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="ea1cd-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="ea1cd-126">Выбор между классом и структурой</span><span class="sxs-lookup"><span data-stu-id="ea1cd-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
