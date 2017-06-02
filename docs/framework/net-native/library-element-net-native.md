---
title: "Элемент &lt;Library&gt; (машинный код .NET) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Элемент &lt;Library&gt; (машинный код .NET)
Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения.  
  
## Синтаксис  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`Name`|Обязательный атрибут.  Задает имя сборки.  Дочерние элементы данного элемента `<Library>` определяют политику отражения среды выполнения для типов и членов типов в этой сборке.|  
  
## Name \- атрибут  
  
|Значение|Описание|  
|--------------|--------------|  
|*assembly\_name*|Простое имя сборки без расширения файла.  Этот атрибут соответствует свойству <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=fullName>.  Например, имя сборки с именем Extensions.dll является «Extensions».  См. раздел Примечания для получения информации об особой форме *assembly\_name* с поддержкой условного включения метаданных из сборки.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<Assembly\>](../../../docs/framework/net-native/assembly-element-net-native.md)|Применяет политику ко всем типам в определенной сборке.|  
|[\<Namespace\>](../../../docs/framework/net-native/namespace-element-net-native.md)|Применяет политику ко всем типам в определенном пространстве имен.|  
|[\<Type\>](../../../docs/framework/net-native/type-element-net-native.md)|Применяет политику для конкретного типа, например, класса или структуры.|  
|[\< TypeInstantiation \>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Применяет политику к сконструированному универсальному типу.  Например, элемент [\< TypeInstantiation \>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) можно использовать для задания политики для типа `List<String>`.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<Directives\>](../../../docs/framework/net-native/directives-element-net-native.md)|Корневой элемент файла директив среды выполнения.|  
  
## Заметки  
 Элемент [\<Directives\>](../../../docs/framework/net-native/directives-element-net-native.md) может иметь ноль, один или более элементов `<Library>`.  
  
 Элемент `<Library>` используется как контейнер для определения программных элементов, метаданные которых требуются во время выполнения. Этот элемент не выражают политики.  Во время компиляции средства компилятора осуществляют поиск только в библиотеке, назначенной с помощью элемента `<Library>`, на наличие программных элементов, определенных его дочерними элементами.  Напротив, средства компилятора выполняют поиск всех библиотек, в том числе основных библиотек .NET Framework, на наличие программных элементов, определенных дочерними элементами элемента  [\<Application\>](../../../docs/framework/net-native/application-element-net-native.md).  
  
 Директивы `<Library>` могут использоваться условно.  Если имя элемента `<Library>` начинается и заканчивается звездочкой \(\*\), директива `<Library>` действует только в том случае, если приложение ссылается на сборку, указанную между звездочками.  Например, следующие директивы среды выполнения применяются только к сборке Utillities.dll, на которую ссылается приложение.  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name=”*Utilities*”>  
   ...  
  </Library>  
</Directives>  
  
```  
  
## См. также  
 [Элемент \<Application\>](../../../docs/framework/net-native/application-element-net-native.md)   
 [Элемент \<Directives\>](../../../docs/framework/net-native/directives-element-net-native.md)   
 [Ссылка на файл конфигурации директив среды выполнения \(rd.xml\)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Элементы директив среды выполнения](../../../docs/framework/net-native/runtime-directive-elements.md)