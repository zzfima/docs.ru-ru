---
title: "Элемент &lt;TimeSpan_LegacyFormatMode&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<TimeSpan_LegacyFormatMode> - элемент"
  - "TimeSpan_LegacyFormatMode - элемент"
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Элемент &lt;TimeSpan_LegacyFormatMode&gt;
Определяет, сохраняет ли среда выполнения устаревшее поведение при операциях форматирования со значениями <xref:System.TimeSpan?displayProperty=fullName>.  
  
## Синтаксис  
  
```  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, использует ли среда выполнения устаревшее поведение форматирования со значениями <xref:System.TimeSpan?displayProperty=fullName>.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|Среда выполнения не восстанавливает устаревшее поведение форматирования.|  
|`true`|Среда выполнения восстанавливает устаревшее поведение форматирования.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## Заметки  
 Начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], структура <xref:System.TimeSpan?displayProperty=fullName> реализует интерфейс <xref:System.IFormattable> и поддерживает операции форматирования со стандартными и пользовательскими строками форматов.  Если метод синтаксического анализа встречает спецификатор неподдерживаемого формата или строку форматирования, он выдает <xref:System.FormatException>.  
  
 В предыдущих версиях .NET Framework структура <xref:System.TimeSpan> не реализовала <xref:System.IFormattable> и не поддерживала строки формата.  Однако многие разработчики ошибочно предположили, что <xref:System.TimeSpan> поддерживает набор строк формата и использовали их в [операциях составного форматирования](../../../../../docs/standard/base-types/composite-formatting.md) с такими методами, как <xref:System.String.Format%2A?displayProperty=fullName>.  Обычно если тип реализует <xref:System.IFormattable> и поддерживает форматирования строки, вызовы методов форматирования с неподдерживаемый формат строки обычно создают <xref:System.FormatException>.  Однако поскольку <xref:System.TimeSpan> не реализует <xref:System.IFormattable>, среда выполнения игнорирует строку формата и вместо этого вызывает метод <xref:System.TimeSpan.ToString?displayProperty=fullName>.  Это означает, что, несмотря на то, что строки формата не имеет влияния на операции форматирования, их наличие не привели к <xref:System.FormatException>.  
  
 Для случаев, в которых устаревший код передает составной метод форматирования и недопустимую строку формата, и код не может быть перекомпилирован, можно использовать элемент `<TimeSpan_LegacyFormatMode>` для восстановления старого поведения <xref:System.TimeSpan>.  Если атрибут `enabled` этого элемента имеет значение `true`, составной метод форматирования приводит к вызову к <xref:System.TimeSpan.ToString?displayProperty=fullName> вместо <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName> и <xref:System.FormatException> не выдается.  
  
## Пример  
 Следующий пример создает экземпляр объекта <xref:System.TimeSpan> и пытается отформатировать его с помощью метода <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=fullName>, используя строку формата неподдерживаемого стандарта.  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 При запуске примера на [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] или на более ранней версии, отображаются следующие выходные данные:  
  
```  
12:30:45  
```  
  
 Это отличается заметно от выходных данных, если выполнить этот пример на [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] или более поздней версии:  
  
```  
Invalid Format  
```  
  
 Однако если добавить следующий файл конфигурации в каталога примера и выполнить пример на [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] или более поздней версии, выходные данные идентичны, созданным в примере при выполнении на [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)