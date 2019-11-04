---
title: Рекомендации по использованию
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: KrzysztofCwalina
ms.openlocfilehash: 23b1520a864d41e5ef59377cc9cca34cbdf22b64
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423051"
---
# <a name="usage-guidelines"></a>Рекомендации по использованию

В этом разделе содержатся рекомендации по использованию распространенных типов в общедоступных API. Он работает с прямым использованием встроенных типов платформы (например, атрибутов сериализации) и перегрузкой общих операторов.
  
Интерфейс <xref:System.IDisposable?displayProperty=nameWithType> не рассматривается в этом разделе, но рассматривается в разделе [шаблон удаления](../garbage-collection/implementing-dispose.md) .

> [!NOTE]
> Рекомендации и дополнительные сведения о других стандартных встроенных типах .NET Framework см. в справочных разделах, посвященных следующим темам: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.

## <a name="in-this-section"></a>В данном разделе

[Массивы](arrays.md)  
[Атрибуты](attributes.md)  
[Коллекции](guidelines-for-collections.md)  
[Сериализация](serialization.md)  
[Использование System.Xml](system-xml-usage.md)  
[Операторы равенства](equality-operators.md)  

*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
