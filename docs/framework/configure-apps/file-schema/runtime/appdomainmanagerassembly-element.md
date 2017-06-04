---
title: "Элемент &lt;appDomainManagerAssembly&gt; | Microsoft Docs"
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
  - "<appDomainManagerAssembly> - элемент"
  - "appDomainManagerAssembly - элемент"
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Элемент &lt;appDomainManagerAssembly&gt;
Задает сборку, предоставляющую диспетчер домена приложения для домена приложения по умолчанию в процессе.  
  
## Синтаксис  
  
```  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`value`|Обязательный атрибут.  Задает отображаемое имя сборки, предоставляющей диспетчер домена приложения для домена приложения по умолчанию в процессе.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 Чтобы задать тип диспетчера домена приложения, необходимо задать как этот элемент, так и элемент [\<appDomainManagerType\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md).  Если один из этих элементов не задан, другой игнорируется.  
  
 При загрузке домена приложения по умолчанию исключение <xref:System.TypeLoadException> создается, если указанная сборка не существует или не содержит тип, заданный элементом [\<appDomainManagerType\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md), и происходит сбой запуска процесса.  Если сборка найдена, но имеет несоответствующие сведения о версии, возникает исключение <xref:System.IO.FileLoadException>.  
  
 Если для домена приложения по умолчанию задан тип диспетчера домена приложения, другие домены приложений, созданные из домена приложения по умолчанию, наследуют тип диспетчера домена приложения.  Чтобы задать для нового домена приложения другой тип диспетчера домена приложения, используйте свойства <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=fullName> и <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=fullName>.  
  
 Для задания типа диспетчера домена приложения требуется, чтобы приложение было полностью доверенным. \(Например, приложение, выполняемое на рабочем столе, имеет полное доверие.\) Если приложение не обладает полным доверием, создается исключение <xref:System.TypeLoadException>.  
  
 Описание формата отображаемого имени сборки см. в описании свойства <xref:System.Reflection.Assembly.FullName%2A?displayProperty=fullName>.  
  
 Этот элемент конфигурации доступен только в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] или более поздних версиях.  
  
## Пример  
 Следующий пример показывает, как задать, что диспетчер домена приложения для домена приложения по умолчанию процесса имеет тип `MyMgr` в сборке `AdMgrExample`.  
  
```  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## См. также  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=fullName>   
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=fullName>   
 [Элемент \<appDomainManagerType\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)   
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Метод SetAppDomainManagerType](../Topic/ICLRControl::SetAppDomainManagerType%20Method.md)