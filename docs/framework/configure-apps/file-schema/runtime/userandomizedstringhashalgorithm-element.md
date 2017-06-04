---
title: "Элемент &lt;UseRandomizedStringHashAlgorithm&gt; | Microsoft Docs"
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
  - "Элемент <UseRandomizedStringHashAlgorithm>"
  - "Элемент UseRandomizedStringHashAlgorithm"
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Элемент &lt;UseRandomizedStringHashAlgorithm&gt;
Определяет, вычисляет ли среда CLR хэш\-коды для строк на основе доменов приложения.  
  
## Синтаксис  
  
```  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, вычисляются ли хэш\-коды для строк для каждого домена приложения.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`0`|Среда CLR не вычисляет хэш\-коды для строк для каждого домена приложения; для вычисления хэш\-кодов строк используется один алгоритм.  Это значение по умолчанию.|  
|`1`|Среда CLR вычисляет хэш\-коды для строк на основе доменов приложения.  Одинаковые строки в разных доменах приложений и в различных процессах будут иметь разные хэш\-коды.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## Заметки  
 По умолчанию класс <xref:System.StringComparer> и метод <xref:System.String.GetHashCode%2A?displayProperty=fullName> использует один алгоритм хэширования, который создает последовательный хэш\-код по доменами приложений.  Это эквивалентно установке атрибута `enabled` элемента `<UseRandomizedStringHashAlgorithm>` в значение `0`.  Это алгоритм хэширования, используемый в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 Класс <xref:System.StringComparer> и метод <xref:System.String.GetHashCode%2A?displayProperty=fullName> также могут использовать другой алгоритм хэширования, который вычисляет хэш\-код для каждого домена приложения.  В результате хэш\-коды для эквивалентных строк будут отличаться в разных доменах приложения.  Эта функция включается по требованию; для ее использования необходимо установить атрибут `enabled` элемента `<UseRandomizedStringHashAlgorithm>` в значение `1`.  
  
 Поиск строки в хэш\-таблице — это обычно операция O \(1\).  Однако если большое количество конфликтов происходит, поиск может стать операцией O\(n<sup>2</sup>\).  Можно использовать элемент конфигурации `<UseRandomizedStringHashAlgorithm>`, который создает случайный алгоритм хэширования в каждом домене приложения, который, в свою очередь, ограничивает число потенциальных конфликтов, особенно если ключи, которые вычисляются хэш\-код, основаны на вводе данных пользователями.  
  
## Пример  
 В следующем примере определяется класс, который включает закрытую строковую константу `s``DisplayString`, имеющую значение "This is a string". Он также включает метод `ShowStringHashCode`, который отображает значение строки и ее хэш\-код вместе с именем домена приложения, в котором метод выполняется.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 При выполнении примера без указания файла конфигурации он отображает подобный следующему вывод.  Обратите внимание, что хэш\-коды для строки идентичны в обоих доменах приложений.  
  
```  
  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
  
```  
  
 Однако при добавлении следующего файла конфигурации в каталог примеров и запуске примера, хэш\-коды для той же строки будут отличаться по домену приложения.  
  
```  
  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
  
```  
  
 Если файл конфигурации существует, пример отображает следующие выходные данные:  
  
```  
  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
  
```  
  
## См. также  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.String.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>