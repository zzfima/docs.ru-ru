---
title: Правила использования
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02905c193387f78430ce1885449055060d07bf82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571037"
---
# <a name="usage-guidelines"></a><span data-ttu-id="4a327-102">Правила использования</span><span class="sxs-lookup"><span data-stu-id="4a327-102">Usage Guidelines</span></span>
<span data-ttu-id="4a327-103">Этот раздел содержит рекомендации по использованию общих типов в общедоступный API.</span><span class="sxs-lookup"><span data-stu-id="4a327-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="4a327-104">Он обрабатывает прямое использование встроенных типов (например, атрибуты сериализации) и Framework перегрузка общих операторов.</span><span class="sxs-lookup"><span data-stu-id="4a327-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>  
  
 <span data-ttu-id="4a327-105"><xref:System.IDisposable?displayProperty=nameWithType> Интерфейс не рассматривается в этом разделе, но рассматривается в [шаблон Dispose](../../../docs/standard/design-guidelines/dispose-pattern.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="4a327-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a327-106">Инструкции и Дополнительные сведения о других типичных, встроенных типов .NET Framework в справочных разделах по следующим: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4a327-106">For guidelines and additional information about about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a327-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4a327-107">In This Section</span></span>  
 [<span data-ttu-id="4a327-108">Массивы</span><span class="sxs-lookup"><span data-stu-id="4a327-108">Arrays</span></span>](../../../docs/standard/design-guidelines/arrays.md)  
 [<span data-ttu-id="4a327-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4a327-109">Attributes</span></span>](../../../docs/standard/design-guidelines/attributes.md)  
 [<span data-ttu-id="4a327-110">Коллекции</span><span class="sxs-lookup"><span data-stu-id="4a327-110">Collections</span></span>](/cpp/mfc/collections)  
 [<span data-ttu-id="4a327-111">Сериализация</span><span class="sxs-lookup"><span data-stu-id="4a327-111">Serialization</span></span>](../../../docs/standard/design-guidelines/serialization.md)  
 [<span data-ttu-id="4a327-112">Использование System.Xml</span><span class="sxs-lookup"><span data-stu-id="4a327-112">System.Xml Usage</span></span>](../../../docs/standard/design-guidelines/system-xml-usage.md)  
 [<span data-ttu-id="4a327-113">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="4a327-113">Equality Operators</span></span>](../../../docs/standard/design-guidelines/equality-operators.md)  
 <span data-ttu-id="4a327-114">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="4a327-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4a327-115">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4a327-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a327-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4a327-116">See Also</span></span>  
 [<span data-ttu-id="4a327-117">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="4a327-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
