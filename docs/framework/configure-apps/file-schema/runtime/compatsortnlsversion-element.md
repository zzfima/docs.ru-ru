---
title: "Элемент &lt;CompatSortNLSVersion&gt; | Microsoft Docs"
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
  - "<CompatSortNLSVersion> - элемент"
  - "CompatSortNLSVersion - элемент"
ms.assetid: 782cc82e-83f7-404a-80b7-6d3061a8b6e3
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Элемент &lt;CompatSortNLSVersion&gt;
Указывает, что при операциях сравнения строк среда выполнения должна использовать устаревший порядок сортировки.  
  
## Синтаксис  
  
```  
<CompatSortNLSVersion    
   enabled="4096"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает код языка, порядок сортировки которого должен использоваться.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|4096|Код языка, представляющий альтернативный порядок сортировки.  В этом случае 4096 представляет порядок сортировки [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] и более ранних версий.|  
  
### Дочерние элементы  
 Отсутствуют.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## Заметки  
 Поскольку операции сравнения, сортировки строк и смены их регистра символов, выполняемые классом <xref:System.Globalization.CompareInfo?displayProperty=fullName> в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], соответствуют стандарту Unicode 5.1, результаты таких методов сравнения строк, как <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=fullName> и <xref:System.String.LastIndexOf%28System.String%29?displayProperty=fullName>, могут отличаться от результатов, получаемых в предыдущих версиях .NET Framework.  Если приложение зависит от устаревшего поведения, можно восстановить правила сравнения и сортировки строк, используемые в [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] и более ранних версиях, включив в файл конфигурации приложения элемент `<CompatSortNLSVersion>`.  
  
> [!IMPORTANT]
>  Для восстановления устаревших правил сравнения и сортировки строк также требуется, чтобы в локальной системе была доступна библиотека динамической компоновки sort00001000.dll.  
  
 Устаревшие правила сортировки и сравнения строк можно также использовать в конкретном домене приложения, передав при создании этого домена строку "NetFx40\_Legacy20SortingBehavior" в метод <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A>.  
  
## Пример  
 В следующем примере создаются экземпляры двух объектов <xref:System.String> и вызывается метод <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=fullName>, чтобы сравнить их с использованием соглашений текущих языка и региональных параметров.  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 При запуске примера в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] отображаются следующие выходные данные.  
  
```  
sta follows a in the sort order.  
```  
  
 Они полностью отличаются от выходных данных, отображаемых при запуске примера в [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```  
sta equals a in the sort order.  
```  
  
 Однако если в каталог примера добавить представленный ниже файл конфигурации и запустить пример в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], выходные данные будут идентичны данным, созданным примером при его запуске в [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)