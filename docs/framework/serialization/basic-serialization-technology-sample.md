---
title: "Образец технологии базовой сериализации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9d824e16-08d1-4a36-bc7f-2388c1f75f34
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Образец технологии базовой сериализации
[Загрузить образец](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)  
  
 В этом образце демонстрируется возможность среды CLR выполнять сериализацию графа объекта в поток.Для сериализации в примере могут использоваться классы <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> или <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.Связанный список, заполненный данными, сериализируется в поток файла или десериализируется из потока файла.В любом случае этот список отображается для того, чтобы можно было видеть результаты.Связанный список является списком типа `LinkedList`, который определен в этом примере.  
  
 Дополнительные сведения о сериализации см. в комментариях к исходному коду и в файлах build.proj.  
  
### Построение образца с использованием командной строки  
  
1.  С помощью командной строки перейдите к одной из вложенных папок в каталоге Technologies\\Serialization\\Runtime Serialization\\Basic, соответствующей выбранному языку.  
  
2.  В командной строке введите **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** или **msbuild SerializationVB.sln**, в зависимости от выбранного языка программирования.  
  
### Построение примера с использованием Visual Studio  
  
1.  Откройте [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] и перейдите к вложенной папке для данного образца, соответствующей выбранному языку.  
  
2.  Дважды щелкните значок файла SerializationCS.sln, SerializationJSL.sln или SerializationVB.sln file, в зависимости от выбранного языка программирования, чтобы открыть файл в Visual Studio.  
  
3.  В меню **Построение** выберите команду **Построить решение**.  
  
 По умолчанию построение образца приложения помещается в подкаталог \\bin или \\bin\\Debug.  
  
### Выполнение примера  
  
1.  Перейдите в каталог, содержащий построенный исполняемый файл.  
  
2.  В командной строке введите **Serialization.exe** вместе с необходимыми значениями параметров.  
  
    > [!NOTE]
    >  В данном образце выполняется построение консольного приложения.Чтобы просмотреть выводимые им данные, необходимо запустить его в командной строке.  
  
## Примечания  
 Образец приложения принимает параметры командной строки, указывающие, какой тест следует выполнить.Чтобы выполнить сериализацию списка из 10 узлов в файл с именем **Test.xml** с помощью модуля форматирования SOAP, используйте параметры **sx Test.xml 10**.  
  
 Например:  
  
 **Serialize.exe \-sx Test.xml 10**  
  
 Чтобы десериализировать файл **Test.xml** из предыдущего примера, используйте параметры **dx Test.xml**.  
  
 Например:  
  
 **Serialize.exe \-dx Test.xml**  
  
 В двух приведенных выше примерах параметр командной строки "x" означает использование сериализации XML SOAP.Вместо этого можно использовать "b" для двоичной сериализации.Если необходимо испытать сериализацию с очень большим числом узлов, может потребоваться перенаправить выходные данные с консоли в файл.  
  
 Например:  
  
 **Serialize.exe \-sb Test.bin 10000 \>somefile.txt**  
  
 В следующем маркированном списке кратко описываются технологии и классы, используемые в этом образце.  
  
-   Сериализация во время выполнения  
  
    -   <xref:System.Runtime.Serialization.IFormatter> Используется для ссылки на объект <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> или <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Используется для сериализации связанного списка в поток двоичного формата.Двоичный модуль форматирования использует формат, который понятен только типу <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.Однако данные являются краткими.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Используется для сериализации связанного списка в поток формата SOAP.SOAP является стандартным форматом.  
  
-   Потоковый ввод\-вывод  
  
    -   <xref:System.IO.Stream> Используется для сериализации и десериализации.Особый тип потока, который используется в этом примере, является типом <xref:System.IO.FileStream>.Однако сериализация может быть использована с любым типом, производным от <xref:System.IO.Stream>.  
  
    -   <xref:System.IO.File> Используется для создания объектов <xref:System.IO.FileStream> для чтения и создания файлов на диске.  
  
    -   <xref:System.IO.FileStream> Используется для сериализации и десериализации связанных списков.  
  
## См. также  
 [Класс BinaryFormatter](frlrfSystemRuntimeSerializationFormattersBinaryBinaryFormatterClassTopic)   
 [Класс File](frlrfSystemIOFileClassTopic)   
 [Класс FileStream](frlrfSystemIOFileStreamClassTopic)   
 [Интерфейс IFormatter](frlrfSystemRuntimeSerializationIFormatterClassTopic)   
 [Класс Random](https://msdn.microsoft.com/en-us/library/system.random.aspx)   
 [Атрибут SerializableAttribute](frlrfSystemSerializableAttributeClassTopic)   
 [Класс SoapFormatter](frlrfSystemRuntimeSerializationFormattersSoapSoapFormatterClassTopic)   
 [Класс Stream](frlrfSystemIOStreamClassTopic)   
 [Пространство имен System.IO](https://msdn.microsoft.com/en-us/library/system.io.aspx)   
 [Пространство имен System.Runtime.Serialization](frlrfSystemRuntimeSerialization)   
 [Пространство имен System.Xml.Serialization](frlrfSystemXmlSerialization)   
 [Базовая сериализация](../../../docs/framework/serialization/basic-serialization.md)   
 [Двоичная сериализация](../../../docs/framework/serialization/binary-serialization.md)   
 [Управление XML\-сериализацией с использованием атрибутов](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)   
 [Введение в XML\-сериализацию](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [Сериализация](../../../docs/framework/serialization/index.md)   
 [SOAP Service](http://msdn.microsoft.com/ru-ru/2051c992-28d1-499e-961f-17e9b675cec9)   
 [XML\- и SOAP\-сериализация](../../../docs/framework/serialization/xml-and-soap-serialization.md)