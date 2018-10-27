---
title: Рекомендации по использованию
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e583bf7768c60477effb6c1cf9b838ae4c8c182
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50042536"
---
# <a name="usage-guidelines"></a><span data-ttu-id="f42a1-102">Рекомендации по использованию</span><span class="sxs-lookup"><span data-stu-id="f42a1-102">Usage guidelines</span></span>

<span data-ttu-id="f42a1-103">Этот раздел содержит рекомендации по использованию распространенных типов в общедоступных API.</span><span class="sxs-lookup"><span data-stu-id="f42a1-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="f42a1-104">Он имеет дело с прямое использование объектов встроенных типов Framework (например, атрибуты сериализации) и перегрузка общих операторов.</span><span class="sxs-lookup"><span data-stu-id="f42a1-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="f42a1-105"><xref:System.IDisposable?displayProperty=nameWithType> Интерфейс в этом разделе не рассматривается, но рассматривается в [шаблон Dispose](../../../docs/standard/design-guidelines/dispose-pattern.md) раздел.</span><span class="sxs-lookup"><span data-stu-id="f42a1-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="f42a1-106">Инструкции и Дополнительные сведения о других типичных, встроенных типов .NET Framework, см. в разделе справочные разделы, в следующих целях: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f42a1-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f42a1-107">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="f42a1-107">In this section</span></span>

[<span data-ttu-id="f42a1-108">Массивы</span><span class="sxs-lookup"><span data-stu-id="f42a1-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="f42a1-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f42a1-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="f42a1-110">Коллекции</span><span class="sxs-lookup"><span data-stu-id="f42a1-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="f42a1-111">Сериализация</span><span class="sxs-lookup"><span data-stu-id="f42a1-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="f42a1-112">Использование System.Xml</span><span class="sxs-lookup"><span data-stu-id="f42a1-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="f42a1-113">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="f42a1-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="f42a1-114">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="f42a1-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="f42a1-115">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f42a1-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f42a1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f42a1-116">See also</span></span>

- [<span data-ttu-id="f42a1-117">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="f42a1-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
