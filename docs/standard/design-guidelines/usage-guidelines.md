---
title: Рекомендации по использованию
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
ms.openlocfilehash: 57f6600f60e99c72b72c9f82856dc9eb631a9d4b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709001"
---
# <a name="usage-guidelines"></a><span data-ttu-id="752c2-102">Рекомендации по использованию</span><span class="sxs-lookup"><span data-stu-id="752c2-102">Usage guidelines</span></span>

<span data-ttu-id="752c2-103">В этом разделе содержатся рекомендации по использованию распространенных типов в общедоступных API.</span><span class="sxs-lookup"><span data-stu-id="752c2-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="752c2-104">Он работает с прямым использованием встроенных типов платформы (например, атрибутов сериализации) и перегрузкой общих операторов.</span><span class="sxs-lookup"><span data-stu-id="752c2-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="752c2-105">Интерфейс <xref:System.IDisposable?displayProperty=nameWithType> не рассматривается в этом разделе, но рассматривается в разделе [шаблон удаления](../garbage-collection/implementing-dispose.md) .</span><span class="sxs-lookup"><span data-stu-id="752c2-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../garbage-collection/implementing-dispose.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="752c2-106">Рекомендации и дополнительные сведения о других стандартных встроенных типах .NET Framework см. в справочных разделах, посвященных следующим темам: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="752c2-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="752c2-107">В данном разделе</span><span class="sxs-lookup"><span data-stu-id="752c2-107">In this section</span></span>

[<span data-ttu-id="752c2-108">Массивы</span><span class="sxs-lookup"><span data-stu-id="752c2-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="752c2-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="752c2-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="752c2-110">Коллекции</span><span class="sxs-lookup"><span data-stu-id="752c2-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="752c2-111">Сериализация</span><span class="sxs-lookup"><span data-stu-id="752c2-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="752c2-112">Использование System.Xml</span><span class="sxs-lookup"><span data-stu-id="752c2-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="752c2-113">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="752c2-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="752c2-114">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="752c2-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="752c2-115">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="752c2-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="752c2-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="752c2-116">See also</span></span>

- [<span data-ttu-id="752c2-117">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="752c2-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
