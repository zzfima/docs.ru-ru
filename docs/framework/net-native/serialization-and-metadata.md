---
title: Сериализация и метаданные
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
ms.openlocfilehash: 1805b6ca06d584237303d1366222419da3e8b9ef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128112"
---
# <a name="serialization-and-metadata"></a>Сериализация и метаданные

Если ваше приложение сериализует и десериализует объекты, может потребоваться добавить записи в файл директив среды выполнения (. rd.xml) файл, чтобы гарантировать наличие необходимых метаданных во время выполнения. Существует две категории сериализаторов, и каждый требует различной обработки в файла директив среды выполнения:  
  
- Сериализиторы сторонних поставщиков на основе отражения. Они требуют изменений в файле директив среды выполнения и рассматриваются в следующем разделе.  
  
- Сериализиторы без отражения содержатся в библиотеке классов платформы .NET Framework. Они могут потребовать внесения изменений в файл директив среды выполнения и обсуждаются в разделе [Сериализаторы Майкрософт](#Microsoft).  
  
<a name="ThirdParty"></a>
## <a name="third-party-serializers"></a>Сериализаторы сторонних поставщиков

 Сериализаторы сторонних поставщиков, включая Newtonsoft.JSON, обычно основаны на отражении. Учитывая большой двоичный объект (BLOB) из сериализованных данных, поля данных назначаются конкретному типу путем поиска полей типа целевого объекта по имени. Как минимум, использование этих библиотек приводит к исключениям [MissingMetadataException](missingmetadataexception-class-net-native.md) для каждого объекта <xref:System.Type> при попытке сериализации или десериализации в коллекции `List<Type>`.  
  
 Самый простой способ решения проблем, вызванных отсутствующими метаданными для этих сериализаторов, состоит в сборе типов, которые будут использоваться при сериализации в одном пространстве имен (например, `App.Models`) и применить к нему директиву метаданных `Serialize`:  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 Информацию о синтаксисе, используемом в примере, см. в разделе [Элемент \<Namespace>](namespace-element-net-native.md).  
  
<a name="Microsoft"></a>
## <a name="microsoft-serializers"></a>Сериализаторы Microsoft

 Несмотря на то, что классы <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> и <xref:System.Xml.Serialization.XmlSerializer> не рассчитывают на отражение, они требуют создания кода на основе объекта для сериализации или десериализации. Перегруженные конструкторы для каждого сериализатора содержа параметр <xref:System.Type>, который задает тип для сериализации или десериализации. Способ указания этого типа в коде определяет действие, которое необходимо выполнить, как описано в следующих двух разделах.  
  
### <a name="typeof-used-in-the-constructor"></a>TypeOf используется в конструкторе

 Если вызвать конструктор этих классов сериализации и включить C# оператор [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) в вызов метода, нет необходимости **выполнять дополнительную работу**. Например, в каждом из следующих вызовов конструктора класса сериализации ключевое слово `typeof`используется как часть выражения, переданного в конструктор.  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 Компилятор .NET Native будет автоматически выполнять этот код.  
  
### <a name="typeof-used-outside-the-constructor"></a>TypeOf, использованный за пределами конструктора

 Если вызвать конструктор этих классов сериализации и использовать C# оператор [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) за пределами выражения, переданного в параметр <xref:System.Type> конструктора, как показано в следующем коде, компилятор .NET Native не может разрешить тип:  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 В этом случае необходимо указать тип в файле директив среды выполнения, добавив следующую запись:  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 Аналогично, если вы вызываете конструктор, например <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType> и предоставляете для сериализации массив дополнительных <xref:System.Type> объектов, как показано в следующем коде, компилятор .NET Native не может разрешить эти типы.  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
 Необходимо добавить следующие записи для каждого типа в файл директив среды выполнения:  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
 Информацию о синтаксисе, используемом в примере, см. в разделе [Элемент \<Type>](type-element-net-native.md).  
  
## <a name="see-also"></a>См. также

- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
- [Элемент > типа\<](type-element-net-native.md)
- [Элемент \<Namespace>](namespace-element-net-native.md)
