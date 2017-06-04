---
title: "Элемент &lt;Directives&gt; (машинный код .NET) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Элемент &lt;Directives&gt; (машинный код .NET)
Корневой элемент в любом файле директив среды выполнения для [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 **\< директивы xmlns \= «http:\/\/schemas.microsoft.com\/netfx\/2013\/01\/metadata» \>**  
  
## Синтаксис  
  
```xml  
  
        <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`xmlns`|Пространство имен XML.  Всегда имеет значение **«http:\/\/schemas.microsoft.com\/netfx\/2013\/01\/metadata»**.|  
  
## Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<Application\>](../../../docs/framework/net-native/application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.|  
|[\<Library\>](../../../docs/framework/net-native/library-element-net-native.md)|Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.|  
  
## Заметки  
 Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.  
  
 Элемент `<Directives>` может содержать ноль или один элемент [\<Application\>](../../../docs/framework/net-native/application-element-net-native.md) и ноль, один или более элементов [\<Library\>](../../../docs/framework/net-native/library-element-net-native.md).  
  
## См. также  
 [Ссылка на файл конфигурации директив среды выполнения \(rd.xml\)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Элементы директив среды выполнения](../../../docs/framework/net-native/runtime-directive-elements.md)