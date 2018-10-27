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
# <a name="usage-guidelines"></a>Рекомендации по использованию

Этот раздел содержит рекомендации по использованию распространенных типов в общедоступных API. Он имеет дело с прямое использование объектов встроенных типов Framework (например, атрибуты сериализации) и перегрузка общих операторов.
  
<xref:System.IDisposable?displayProperty=nameWithType> Интерфейс в этом разделе не рассматривается, но рассматривается в [шаблон Dispose](../../../docs/standard/design-guidelines/dispose-pattern.md) раздел.

> [!NOTE]
> Инструкции и Дополнительные сведения о других типичных, встроенных типов .NET Framework, см. в разделе справочные разделы, в следующих целях: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.

## <a name="in-this-section"></a>Содержание раздела

[Массивы](arrays.md)  
[Атрибуты](attributes.md)  
[Коллекции](guidelines-for-collections.md)  
[Сериализация](serialization.md)  
[Использование System.Xml](system-xml-usage.md)  
[Операторы равенства](equality-operators.md)  

*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*

*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
