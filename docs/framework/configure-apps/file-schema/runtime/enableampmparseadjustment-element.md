---
title: Элемент <EnableAmPmParseAdjustment>
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d1a14199debbb90827c1ea95347d485a636329
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704847"
---
# <a name="enableampmparseadjustment-element"></a>\<EnableAmPmParseAdjustment > элемент
Определяет методы анализа даты и времени использования скорректированной набор правил для анализа строк даты, которые содержат день, месяц, час и указатель AM/PM.  
  
 \<configuration>  
 \<Среда выполнения >  
\<EnableAmPmParseAdjustment >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Разрешение методы анализа даты и времени скорректированной набор правил для анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.|  
  
### <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|0|Методы анализа даты и времени не используйте скорректированное правил для анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.|  
|1|Методы анализа даты и времени скорректированной правила можно использовать для синтаксического анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 `<EnableAmPmParseAdjustment>` Элемент управляет как следующие методы проанализировать строку даты, который содержит числовой день и месяц, за которым следует один час и указатель AM/PM (например, «6 4/10 AM»):  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 Другие шаблоны не затрагиваются.  
  
 `<EnableAmPmParseAdjustment>` Элемент не оказывает влияния на <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, и <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> методы.  
  
> [!IMPORTANT]
>  В .NET Core и .NET Native скорректированное правила анализа AM/PM включены по умолчанию.  
  
 Если синтаксического анализа правило коррекции не включена, первая цифра строка интерпретируется как час 12-часовом формате и учитывается в оставшейся части строки, за исключением указатель AM/PM. Дата и время, возвращаемых методом анализа состоит из текущей даты и часа дня, извлеченных из строки даты.  
  
 Если включен синтаксический анализ правила коррекции, методу анализа интерпретировать день и месяц как относящиеся к текущему году и интерпретировать времени в формате часа 12-часовом формате.  
  
 В следующей таблице показаны различия в <xref:System.DateTime> значения при <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> метод используется для анализа строки ««4/10 6 AM» с `<EnableAmPmParseAdjustment>` элемента `enabled` свойству присвоено значение «0» или «1». Предполагается, что сегодняшняя дата 5 января 2017 г. и отображает дату, как если бы он отформатирован с помощью строки формата «G» для указанного языка и региональных параметров.  
  
|Имя языка и региональных параметров|enabled="0"|enabled="1"|  
|------------------|------------------|------------------|  
|en-US|1/5/2017 4:00:00 AM|4/10/2017 06:00:00: 00|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>См. также

- [\<Среда выполнения > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [Элемент \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
