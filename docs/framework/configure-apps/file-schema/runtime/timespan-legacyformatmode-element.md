---
title: Элемент <TimeSpan_LegacyFormatMode>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38adde3cd51a96f0e15ed5a0c539e088f2d3b480
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164558"
---
# <a name="timespanlegacyformatmode-element"></a>\<TimeSpan_LegacyFormatMode > элемент
Определяет, сохраняет ли среда выполнения устаревшее поведение в операциях с форматирования <xref:System.TimeSpan?displayProperty=nameWithType> значения.  
  
 \<configuration>  
\<Среда выполнения >  
< TimeSpan_LegacyFormatMode >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, использует ли среда выполнения устаревшее поведение форматирования с <xref:System.TimeSpan?displayProperty=nameWithType> значения.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Среда выполнения не восстанавливает устаревшее поведение форматирования.|  
|`true`|Среда выполнения восстанавливает устаревшее поведение форматирования.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], <xref:System.TimeSpan?displayProperty=nameWithType> структура реализует <xref:System.IFormattable> интерфейс и поддерживает операций со строками формата стандартные и настраиваемые форматирования. Если метод синтаксического анализа встречается описатель неподдерживаемый формат или строка формата, он выдает <xref:System.FormatException>.  
  
 В предыдущих версиях .NET Framework <xref:System.TimeSpan> структуры не реализовал <xref:System.IFormattable> и не поддерживает строки формата. Тем не менее, многие разработчики ошибочно полагают, что <xref:System.TimeSpan> поддерживали набор строк формата, которые использовались в [составного форматирования операций](../../../../../docs/standard/base-types/composite-formatting.md) с помощью методов, таких как <xref:System.String.Format%2A?displayProperty=nameWithType>. Как правило если тип реализует <xref:System.IFormattable> и поддерживает формат строки, вызовы методов форматирования с неподдерживаемый формат строки обычно throw <xref:System.FormatException>. Тем не менее так как <xref:System.TimeSpan> не реализовал <xref:System.IFormattable>, среда выполнения, игнорируется строка форматирования и вместо этого вызов <xref:System.TimeSpan.ToString?displayProperty=nameWithType> метод. Это означает, что, несмотря на то, что строки формата не оказывает никакого влияния на операции форматирования, их наличие не привели к <xref:System.FormatException>.  
  
 Для случаев, в которых устаревший код передает составного форматирования метода и Недопустимая строка форматирования, а не удается заново скомпилировать этот код, можно использовать `<TimeSpan_LegacyFormatMode>` элемента для восстановления предыдущих версий <xref:System.TimeSpan> поведение. При задании `enabled` атрибут этого элемента к `true`, составного форматирования результаты метода в вызове <xref:System.TimeSpan.ToString?displayProperty=nameWithType> вместо <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>и <xref:System.FormatException> не создается.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.TimeSpan> объекта и предпринимает попытку отформатировать его с <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> метод с использованием строки стандартного формата, не поддерживается.  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 При запуске примера в [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] или на более ранней версии, отображает следующие выходные данные:  
  
```  
12:30:45  
```  
  
 Они сильно отличаются от выходных данных, получаемых при выполнении примера в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] или более поздней версии:  
  
```  
Invalid Format  
```  
  
 Однако если в каталог примера добавить представленный ниже файл конфигурации и запустить пример в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] или более поздней версии, выходные данные будут идентичны данным, созданным примером при его запуске в [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
