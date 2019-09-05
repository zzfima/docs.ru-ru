---
title: Элемент <EnableAmPmParseAdjustment>
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f132ce0a114a6fc904d86ca3ce893c447366523f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252629"
---
# <a name="enableampmparseadjustment-element"></a>\<Элемент > Енаблеампмпарсеаджустмент
Определяет, используют ли методы синтаксического анализа даты и времени настроенный набор правил для синтаксического анализа строк даты, содержащих день, месяц, час и обозначение AM/PM.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<Енаблеампмпарсеаджустмент >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, используют ли методы синтаксического анализа даты и времени настроенный набор правил для анализа строк даты, содержащих только день, месяц, час и обозначение AM/PM.|  
  
### <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|0|Методы синтаксического анализа даты и времени не используют скорректированные правила для анализа строк даты, содержащих только день, месяц, час и обозначение AM/PM.|  
|1|Методы синтаксического анализа даты и времени используют скорректированные правила для анализа строк даты, содержащих только день, месяц, час и обозначение AM/PM.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 `<EnableAmPmParseAdjustment>` Элемент определяет, как следующие методы анализируют строку даты, которая содержит числовой день и месяц, за которыми следует час и обозначение AM/PM (например, "4/10 6 AM"):  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 Другие шаблоны не затрагиваются.  
  
 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType> <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>Элемент не влияет на методы,, и<xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> . `<EnableAmPmParseAdjustment>`  
  
> [!IMPORTANT]
> В .NET Core и .NET Native настроенные правила анализа AM/PM включены по умолчанию.  
  
 Если правило коррекции синтаксического анализа не включено, первая цифра строки интерпретируется как час 12-часового времени, а оставшаяся часть строки, за исключением обозначения AM/PM, игнорируется. Дата и время, возвращаемые методом анализа, состоят из текущей даты и часа дня, извлеченных из строки даты.  
  
 Если правило коррекции синтаксического анализа включено, метод синтаксического анализа интерпретирует день и месяц как принадлежащий текущему году и интерпретирует время как час 12-часового времени.  
  
 В следующей таблице <xref:System.DateTime> показано различие в значении, <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> когда метод используется для синтаксического анализа строки "" `<EnableAmPmParseAdjustment>` 4/10 6 AM `enabled` "со свойством элемента, имеющим значение" 0 "или" 1 ". Предполагается, что сегодняшняя дата — 5 января 2017, а дата отображается так, как если бы она была отформатирована с использованием строки формата "G" указанного языка и региональных параметров.  
  
|Имя языка и региональных параметров|Enabled = "0"|enabled="1"|  
|------------------|------------------|------------------|  
|en-US|1/5/2017 4:00:00 AM|4/10/2017 6:00:00 AM|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>См. также

- [\<Элемент > среды выполнения](runtime-element.md)
- [Элемент \<configuration>](../configuration-element.md)
