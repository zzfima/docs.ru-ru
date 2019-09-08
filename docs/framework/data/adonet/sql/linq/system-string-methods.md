---
title: Методы System.String
ms.date: 03/30/2017
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
ms.openlocfilehash: 583c0d58562c1605f24b61489d481e19248ebed4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792492"
---
# <a name="systemstring-methods"></a>Методы System.String
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает следующие методы <xref:System.String>.  
  
## <a name="unsupported-systemstring-methods-in-general"></a>Неподдерживаемые методы System.String в целом  
 Далее представлены общие сведения о неподдерживаемых методах <xref:System.String>.  
  
- Перегрузки с учетом языка и региональных параметров ( `CultureInfo`методы, принимающие  /   /  `StringComparison` `IFormatProvider`).  
  
- Методы, которые принимают или создают массивы значений типа `char`.  
  
## <a name="unsupported-systemstring-static-methods"></a>Неподдерживаемые статические методы System.String  
  
|Неподдерживаемые статические методы System.String|  
|----------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|  
  
## <a name="unsupported-systemstring-non-static-methods"></a>Неподдерживаемые методы System.String, не являющиеся статическими  
  
|Неподдерживаемые методы System.String, не являющиеся статическими|  
|---------------------------------------------------|  
|<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.Split%2A?displayProperty=nameWithType>|  
|<xref:System.String.ToCharArray?displayProperty=nameWithType>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
  
## <a name="differences-from-net"></a>Отличия от платформы .NET  
  
- Запросы не учитывают параметры сортировки SQL Server, которые могут применяться на сервере, и поэтому по умолчанию выполняют сравнения, зависящие от языка и региональных параметров и не зависящие от регистра. Это поведение отличается от семантики платформы .NET Framework, по умолчанию учитывающей регистр.  
  
- Если `LastIndexOf` функция возвращает значение 0, то либо `NULL` строка имеет значение, либо найденная позицией имеет значение 0.  
  
- При объединении строк фиксированной длины (`CHAR`, `NCHAR`) или выполнении других операций над этими строками могут возвращаться непредвиденные результаты, поскольку к этим типам применяется автоматическое заполнение в базе данных.  
  
- Для многих методов, таких как `Replace`, `ToLower`, `ToUpper` и индексатор знаков, не предусмотрено допустимого предобразования столбцов или кода XML типа `TEXT` или `NTEXT`, поэтому при их преобразовании, как правило, вызываются исключения `SqlExceptions`. Это поведения считается допустимым для этих типов. Однако все операции над строками должны соответствовать семантике среды CLR для типов `VARCHAR`, `NVARCHAR`, `VARCHAR(max)` и `NVARCHAR(max)`.  
  
## <a name="see-also"></a>См. также

- [Типы данных и функции](data-types-and-functions.md)
