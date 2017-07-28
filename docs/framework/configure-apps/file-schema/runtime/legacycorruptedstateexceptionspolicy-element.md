---
title: "Элемент &lt;legacyCorruptedStateExceptionsPolicy&gt; | Microsoft Docs"
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
  - "<legacyCorruptedStateExceptionsPolicy> - элемент"
  - "legacyCorruptedStateExceptionsPolicy - элемент"
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Элемент &lt;legacyCorruptedStateExceptionsPolicy&gt;
Задает, разрешает ли среда CLR управляемому коду перехватывать нарушения прав доступа и другие исключения поврежденного состояния.  
  
## Синтаксис  
  
```  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Задает, что приложение будет перехватывать сбои из\-за исключений поврежденного состояния, такие как нарушения прав доступа.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|Приложение не будет перехватывать сбои из\-за исключений поврежденного состояния, такие как нарушения прав доступа.  Это значение по умолчанию.|  
|`true`|Приложение будет перехватывать сбои из\-за исключений поврежденного состояния, такие как нарушения прав доступа.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 В платформе .NET Framework версии 3.5 и более ранних версий среда CLR разрешала управляемому коду перехватывать исключения, созданные в результате поврежденных состояний процесса.  Нарушение прав доступа — это пример исключения такого типа.  
  
 Начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], управляемый код больше не перехватывает исключения таких типов в блоках `catch`.  Однако можно переопределить это изменение и продолжить обработку исключений поврежденных состояний одним из двух способов:  
  
-   Задать в элементе `<legacyCorruptedStateExceptionsPolicy>` для атрибута `enabled` значение `true`.  Этот параметр конфигурации применяется целиком к процессу и влияет на все методы.  
  
 – или –  
  
-   Применить атрибут <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName> к методу, содержащему блок `catch` для этих исключений.  
  
 Этот элемент конфигурации доступен только в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] или более поздних версиях.  
  
## Пример  
 В следующем примере показано, как задать, что в приложении должно использоваться поведение до [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] и перехватываться все сбои, связанные с исключениями поврежденного состояния.  
  
```  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## См. также  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>   
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)