---
title: "&lt;EnableAmPmParseAdjustment&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 44bd6297142b6f29d93e9a3bebdb89d32d4bf46a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltenableampmparseadjustmentgt-element"></a>&lt;EnableAmPmParseAdjustment&gt; элемент
Определяет дату и время методов синтаксического анализа использования скорректированное набор правил, выполнить синтаксический анализ строк даты, которые содержат день, месяц, часов и обозначение AM/PM.  
  
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает дату и время методов синтаксического анализа использования скорректированное набор правил, выполнить синтаксический анализ строк даты, которые содержат только день, месяц, часов и обозначение AM/PM.|  
  
### <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|0|Дата и время методов синтаксического анализа не использовать скорректированное правила для разбора строки даты, которые содержат только день, месяц, часов и обозначение AM/PM.|  
|1|Дата и время методов синтаксического анализа скорректированное правила можно использовать для синтаксического анализа строки даты, которые содержат только день, месяц, часов и обозначение AM/PM.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 `<EnableAmPmParseAdjustment>` Элемент управляет как следующие методы синтаксический анализ строки даты, содержащий числовое значение дня и месяца, за которым следует один час и обозначение AM/PM (например, «4/10 6 AM»):  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 Другие шаблоны не затрагиваются.  
  
 `<EnableAmPmParseAdjustment>` Элемент не оказывает влияния на <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, и <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> методы.  
  
> [!IMPORTANT]
>  В .NET Core и .NET Native скорректированное правила синтаксического разбора AM/PM включены по умолчанию.  
  
 Если правила коррекции синтаксического анализа не включен, первая цифра строки интерпретируется как час в 12-часовом формате и остальная часть строки, за исключением обозначение AM/PM игнорируется. Дата и время возврата с помощью метода анализа состоит из текущей даты и времени извлекается из строки даты.  
  
 При включении синтаксического анализа правила коррекции анализ метод интерпретировать день и месяц как принадлежащие текущий год и интерпретировать время как час в 12-часовом формате.  
  
 В следующей таблице показаны различия в <xref:System.DateTime> значения при <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> метод используется для анализа строки ««4/10 6 AM» с `<EnableAmPmParseAdjustment>` элемента `enabled` свойством, имеющим значение «0» или «1». Он предполагается, что сегодняшняя дата — 5 января 2017 г. и отображает дату, как если бы он отформатирован с помощью строки формата «G» для указанного языка и региональных параметров.  
  
|Имя языка и региональных параметров|Включить = «0»|Включить = «1»|  
|------------------|------------------|------------------|  
|ru-RU|1/5/2017 Г 4:00:00 AM|4/10/2017 Г. 6:00:00 AM|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>См. также  
 [\<Среда выполнения > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
 [Элемент \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
