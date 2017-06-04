---
title: "Сериализация и метаданные | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Сериализация и метаданные
Если ваше приложение сериализует и десериализует объекты, может потребоваться добавить записи в файл директив среды выполнения \(. rd.xml\) файл, чтобы гарантировать наличие необходимых метаданных во время выполнения.  Существует две категории сериализаторов, и каждый требует различной обработки в файла директив среды выполнения:  
  
-   Сериализиторы сторонних поставщиков на основе отражения.  Они требуют изменений в файле директив среды выполнения и рассматриваются в следующем разделе.  
  
-   Сериализиторы без отражения содержатся в библиотеке классов платформы .NET Framework.  Они могут потребовать внесения изменений в файл директив среды выполнения и обсуждаются в разделе [Сериализаторы Microsoft](#Microsoft).  
  
<a name="ThirdParty"></a>   
## Сериализаторы сторонних поставщиков  
 Сериализаторы сторонних поставщиков, включая Newtonsoft.JSON, обычно основаны на отражении.  Учитывая большой двоичный объект \(BLOB\) из сериализованных данных, поля данных назначаются конкретному типу путем поиска полей типа целевого объекта по имени.  Как минимум, использование этих библиотек приводит к исключениям  [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) для каждого объекта <xref:System.Type>, при попытке сериализации или десериализации в коллекции `List<Type>`.  
  
 Самый простой способ решения проблем, вызванных отсутствующими метаданными для этих сериализаторов, состоит в сборе типов, которые будут использоваться при сериализации в одном пространстве имен \(например, `App.Models`\) и применить к нему директиву метаданных `Serialize`:  
  
```  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 Информацию о синтаксисе, используемом в примере, см. в разделе [Элемент \<Namespace\>](../../../docs/framework/net-native/namespace-element-net-native.md).  
  
<a name="Microsoft"></a>   
## Сериализаторы Microsoft  
 Несмотря на то, что классы <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> и <xref:System.Xml.Serialization.XmlSerializer> не рассчитывают на отражение, они требуют создания кода на основе объекта для сериализации или десериализации.  Перегруженные конструкторы для каждого сериализатора содержа параметр <xref:System.Type>, который задает тип для сериализации или десериализации.  Способ указания этого типа в коде определяет действие, которое необходимо выполнить, как описано в следующих двух разделах.  
  
### TypeOf используется в конструкторе  
 Если вызвать конструктор этих классов сериализации и включить ключевое слово C\# [typeof](../Topic/typeof%20\(C%23%20Reference\).md) в вызов метода, **не нужно прикладывать дополнительные усилия,**.  Например, в каждом из следующих вызовов конструктора класса сериализации ключевое слово `typeof`используется как часть выражения, переданного в конструктор.  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 Компилятор [!INCLUDE[net_native](../../../includes/net-native-md.md)] автоматически будет обрабатывать этот код.  
  
### TypeOf, использованный за пределами конструктора  
 Если вызвать конструктор этих классов сериализации и использовать ключевое слово C\# [typeof](../Topic/typeof%20\(C%23%20Reference\).md) за пределами выражения, предоставленного для параметра <xref:System.Type>конструктора, как в следующем коде, компилятор [!INCLUDE[net_native](../../../includes/net-native-md.md)] не может разрешить тип:  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 В этом случае необходимо указать тип в файле директив среды выполнения, добавив следующую запись:  
  
```  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 Аналогичным образом, если вызвать конструктор [XmlSerializer.XmlSerializer\(Type, Type\<xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=fullName> и предоставить массив дополнительных объектов <xref:System.Type> для сериализации, как показано в следующем коде, компилятору [!INCLUDE[net_native](../../../includes/net-native-md.md)] не удается разрешить эти типы.  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
 Необходимо добавить следующие записи для каждого типа в файл директив среды выполнения:  
  
```  
<Type Name="t" Browse="Required Public" />  
```  
  
 Информацию о синтаксисе, используемом в примере, см. в разделе [Элемент \<Type\>](../../../docs/framework/net-native/type-element-net-native.md).  
  
## См. также  
 [Ссылка на файл конфигурации директив среды выполнения \(rd.xml\)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Элементы директив среды выполнения](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Элемент \<Type\>](../../../docs/framework/net-native/type-element-net-native.md)   
 [Элемент \<Namespace\>](../../../docs/framework/net-native/namespace-element-net-native.md)