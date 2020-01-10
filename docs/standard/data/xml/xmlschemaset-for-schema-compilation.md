---
title: XmlSchemaSet для компиляции схемы
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 55c4b175-3170-4071-9d60-dd5a42f79b54
ms.openlocfilehash: 55347de81c65b7390584415dd29044f4ca4ba02a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709820"
---
# <a name="xmlschemaset-for-schema-compilation"></a>XmlSchemaSet для компиляции схемы
Описывает класс <xref:System.Xml.Schema.XmlSchemaSet>, который представляет собой кэш, в котором можно хранить и проверять схемы XSD.  
  
## <a name="the-xmlschemaset-class"></a>Класс XmlSchemaSet  
 Класс <xref:System.Xml.Schema.XmlSchemaSet> - это кэш, в котором можно хранить и проверять схемы XSD.  
  
 В <xref:System.Xml?displayProperty=nameWithType> версии 1.0 схемы XML загружались в класс <xref:System.Xml.Schema.XmlSchemaCollection> как в библиотеку схем. В <xref:System.Xml?displayProperty=nameWithType> версии 2.0 классы <xref:System.Xml.XmlValidatingReader> и <xref:System.Xml.Schema.XmlSchemaCollection> устарели и были заменены методами <xref:System.Xml.XmlReader.Create%2A> и классом <xref:System.Xml.Schema.XmlSchemaSet>, соответственно.  
  
 Класс <xref:System.Xml.Schema.XmlSchemaSet> был введен, чтобы устранить ряд проблем, в том числе совместимости со стандартами, производительности и устаревшего формата схемы Microsoft XDR.  
  
 Ниже дано сравнение класса <xref:System.Xml.Schema.XmlSchemaCollection> с классом <xref:System.Xml.Schema.XmlSchemaSet>.  
  
|XmlSchemaCollection.|XmlSchemaSet|  
|-------------------------|------------------|  
|Поддерживает схемы Microsoft XDR и W3C XML.|Поддерживает только схемы W3C XML.|  
|Схемы компилируются при вызове метода <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A>.|Схемы не компилируются при вызове метода <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>. В результате повышается производительность при создании библиотеки схем.|  
|Каждая схема формирует отдельную скомпилированную версию, что может привести к созданию «островов схем», т. е. изолированных групп схем. В результате все включения и импорты ограничиваются только этой схемой.|Скомпилированные схемы формируют единую логическую схему, «набор» схем. Любые импортированные схемы внутри схемы, добавленные в набор, сами напрямую добавляются в набор. Это означает, что все типы доступны всем схемам.|  
|Для определенного целевого пространства имен в коллекции может существовать только одна схема.|Для одного целевого пространства имен может быть добавлено несколько схем, если не возникает конфликтов типов.|  
  
## <a name="migrating-to-the-xmlschemaset"></a>Переход на класс XmlSchemaSet  
 В следующем примере кода даны инструкции по переходу на новый класс <xref:System.Xml.Schema.XmlSchemaSet> с устаревшего класса <xref:System.Xml.Schema.XmlSchemaCollection>. В примере кода показаны следующие важные различия между двумя классами.  
  
- В отличие от метода <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> класса <xref:System.Xml.Schema.XmlSchemaCollection>, при вызове метода <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> класса <xref:System.Xml.Schema.XmlSchemaSet> схемы не компилируются. В примере кода явно вызывается метод <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> класса <xref:System.Xml.Schema.XmlSchemaSet>.  
  
- Для итераций по классу <xref:System.Xml.Schema.XmlSchemaSet> необходимо использовать свойство <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> класса <xref:System.Xml.Schema.XmlSchemaSet>.  
  
 Пример устаревшего кода с классом <xref:System.Xml.Schema.XmlSchemaCollection>.  
  
```vb  
Dim schemaCollection As XmlSchemaCollection = New XmlSchemaCollection()  
schemaCollection.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaCollection.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema in schemaCollection  
  
   Console.WriteLine(schema.TargetNamespace)  
  
Next  
```  
  
```csharp  
XmlSchemaCollection schemaCollection = new XmlSchemaCollection();  
schemaCollection.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaCollection.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
  
foreach(XmlSchema schema in schemaCollection)  
{  
   Console.WriteLine(schema.TargetNamespace);  
}  
```  
  
 Пример эквивалентного кода с классом <xref:System.Xml.Schema.XmlSchemaSet>.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Compile()  
  
Dim schema As XmlSchema  
  
For Each schema in schemaSet.Schemas()  
  
   Console.WriteLine(schema.TargetNamespace)  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Compile();  
  
foreach(XmlSchema schema in schemaSet.Schemas())  
{  
   Console.WriteLine(schema.TargetNamespace);  
}  
```  
  
## <a name="adding-and-retrieving-schemas"></a>Добавление и получение схем  
 Схемы добавляются к классу <xref:System.Xml.Schema.XmlSchemaSet> с помощью метода <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> класса <xref:System.Xml.Schema.XmlSchemaSet>. Когда схема добавляется в класс <xref:System.Xml.Schema.XmlSchemaSet>, она связывается с URI-кодом целевого пространства имен. URI-код целевого пространства имен указывается как параметр метода <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>, или, если целевое пространство имен не задано, класс <xref:System.Xml.Schema.XmlSchemaSet> использует целевое пространство имен, определенное в схеме.  
  
 Схемы получаются из класса <xref:System.Xml.Schema.XmlSchemaSet> с помощью свойства <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> класса <xref:System.Xml.Schema.XmlSchemaSet>. Свойство <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> класса <xref:System.Xml.Schema.XmlSchemaSet> позволяет выполнить итерацию по объектам <xref:System.Xml.Schema.XmlSchema>, содержащимся в классе <xref:System.Xml.Schema.XmlSchemaSet>. Свойство <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> возвращает все объекты <xref:System.Xml.Schema.XmlSchema>, содержащиеся в классе <xref:System.Xml.Schema.XmlSchemaSet>, или, при указании параметра целевого пространства имен, возвращает все объекты <xref:System.Xml.Schema.XmlSchema>, которые принадлежат целевому пространству имен. Если в качестве параметра целевого пространства имен указано `null`, свойство <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> возвращает все схемы без пространства имен.  
  
 В следующем примере схема `books.xsd` из пространства имен `http://www.contoso.com/books` добавляется в класс <xref:System.Xml.Schema.XmlSchemaSet>, затем из класса `http://www.contoso.com/books` получаются все схемы, принадлежащие к пространству имен <xref:System.Xml.Schema.XmlSchemaSet>, и записываются в объект <xref:System.Console>.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet  
schemaSet.Add("http://www.contoso.com/books", "books.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema In schemaSet.Schemas("http://www.contoso.com/books")  
  
   schema.Write(Console.Out)  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/books", "books.xsd");  
  
foreach (XmlSchema schema in schemaSet.Schemas("http://www.contoso.com/books"))  
{  
   schema.Write(Console.Out);  
}  
```  
  
 Дополнительные сведения о добавлении и извлечении схем из класса <xref:System.Xml.Schema.XmlSchemaSet> см. в справочной документации по методу <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> и свойству <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>.  
  
## <a name="compiling-schemas"></a>Компиляция схем  
 Схемы в классе <xref:System.Xml.Schema.XmlSchemaSet> компилируются в одну логическую схему с помощью метода <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> класса <xref:System.Xml.Schema.XmlSchemaSet>.  
  
> [!NOTE]
> В отличие от устаревшего класса <xref:System.Xml.Schema.XmlSchemaCollection>, при вызове метода <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> схемы не компилируются.  
  
 Если метод <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> выполняется успешно, свойство <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> класса <xref:System.Xml.Schema.XmlSchemaSet> имеет значение `true`.  
  
> [!NOTE]
> Свойство <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> не изменяется, если изменяются схемы в классе <xref:System.Xml.Schema.XmlSchemaSet>. Обновления отдельных схем в классе <xref:System.Xml.Schema.XmlSchemaSet> не отслеживаются. В результате свойство <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> может иметь значение `true`, даже если одна из схем в классе <xref:System.Xml.Schema.XmlSchemaSet> была изменена, но схемы не добавлялись и не удалялись из класса <xref:System.Xml.Schema.XmlSchemaSet>.  
  
 В следующем примере файл `books.xsd` добавляется в класс <xref:System.Xml.Schema.XmlSchemaSet>, а затем вызывается метод <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/books", "books.xsd")  
schemaSet.Compile()  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/books", "books.xsd");  
schemaSet.Compile();  
```  
  
 Дополнительные сведения о компиляции схем в объекте <xref:System.Xml.Schema.XmlSchemaSet> см. в справочной документации по методу <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>.  
  
## <a name="reprocessing-schemas"></a>Повторная обработка схем  
 При повторной обработке схемы в классе <xref:System.Xml.Schema.XmlSchemaSet> выполняются все шаги предварительной обработки, выполняемые при вызове метода <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> класса <xref:System.Xml.Schema.XmlSchemaSet>. Если метод <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> выполнен успешно, свойство <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> класса <xref:System.Xml.Schema.XmlSchemaSet> имеет значение `false`.  
  
 Метод <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> должен использоваться, когда схема в классе <xref:System.Xml.Schema.XmlSchemaSet> была изменена после выполнения компиляции классом <xref:System.Xml.Schema.XmlSchemaSet>.  
  
 В следующем примере показана повторная обработка схемы, добавленной в класс <xref:System.Xml.Schema.XmlSchemaSet> с использованием метода <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>. После того, как класс <xref:System.Xml.Schema.XmlSchemaSet> скомпилирован с использованием метода <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>, и схема, добавленная в <xref:System.Xml.Schema.XmlSchemaSet>, изменена, свойство <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> имеет значение `true`, даже если схема в классе <xref:System.Xml.Schema.XmlSchemaSet> была изменена. При вызове метода <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> выполняется вся предварительная обработка с использованием метода <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>, и свойство <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> устанавливается в значение `false`.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
Dim schema As XmlSchema = schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Compile()  
  
Dim element As XmlSchemaElement = New XmlSchemaElement()  
schema.Items.Add(element)  
element.Name = "book"  
element.SchemaTypeName = New XmlQualifiedName("string", "http://www.w3.org/2001/XMLSchema")  
  
schemaSet.Reprocess(schema)  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
XmlSchema schema = schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Compile();  
  
XmlSchemaElement element = new XmlSchemaElement();  
schema.Items.Add(element);  
element.Name = "book";  
element.SchemaTypeName = new XmlQualifiedName("string", "http://www.w3.org/2001/XMLSchema");  
  
schemaSet.Reprocess(schema);  
```  
  
 Дополнительные сведения о повторной обработке схем в классе <xref:System.Xml.Schema.XmlSchemaSet> см. в справочной документации по методу <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>.  
  
## <a name="checking-for-a-schema"></a>Проверка наличия схемы  
 Метод <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> класса <xref:System.Xml.Schema.XmlSchemaSet> можно использовать для проверки, что схема содержится в классе <xref:System.Xml.Schema.XmlSchemaSet>. Метод <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> принимает целевое пространство имен или объект <xref:System.Xml.Schema.XmlSchema> для проверки. Метод <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> возвращает значение `true` если схема содержится в классе <xref:System.Xml.Schema.XmlSchemaSet>; в противном случае возвращается значение `false`.  
  
 Дополнительные сведения о проверке наличия схемы см. в справочной документации по методу <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>.  
  
## <a name="removing-schemas"></a>Удаление схем  
 Схемы удаляются из класса <xref:System.Xml.Schema.XmlSchemaSet> с помощью методов <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> и <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> класса <xref:System.Xml.Schema.XmlSchemaSet>. Метод <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> удаляет указанную схему из класса <xref:System.Xml.Schema.XmlSchemaSet>, а метод <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> удаляет из класса <xref:System.Xml.Schema.XmlSchemaSet> указанную схему и все схемы, импортированные ей.  
  
 В следующем примере продемонстрировано добавление нескольких схем в класс <xref:System.Xml.Schema.XmlSchemaSet> с последующим использованием метода <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> для удаления одной из схем и всех импортированных ей схем.  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Add("http://www.contoso.com/music", "http://www.contoso.com/music.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema In schemaSet.Schemas()  
  
   If schema.TargetNamespace = "http://www.contoso.com/music" Then  
      schemaSet.RemoveRecursive(schema)  
   End If  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Add("http://www.contoso.com/music", "http://www.contoso.com/music.xsd");  
  
foreach (XmlSchema schema in schemaSet.Schemas())  
{  
   if (schema.TargetNamespace == "http://www.contoso.com/music")  
   {  
      schemaSet.RemoveRecursive(schema);  
   }  
}  
```  
  
 Дополнительные сведения об удалении схем из класса <xref:System.Xml.Schema.XmlSchemaSet> см. в справочной документации по методам <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> и <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>.  
  
## <a name="schema-resolution-and-xsimport"></a>Разрешение схем и xs:import  
 В следующих примерах описано поведение класса <xref:System.Xml.Schema.XmlSchemaSet> при импорте схем и существовании в классе <xref:System.Xml.Schema.XmlSchemaSet> нескольких схем для данного пространства имен.  
  
 Например, рассмотрим класс <xref:System.Xml.Schema.XmlSchemaSet>, содержащий несколько схем пространства имен `http://www.contoso.com`. Схема со следующей директивой `xs:import` добавлена в класс <xref:System.Xml.Schema.XmlSchemaSet>.  
  
```xml  
<xs:import namespace="http://www.contoso.com" schemaLocation="http://www.contoso.com/schema.xsd" />  
```  
  
 Класс <xref:System.Xml.Schema.XmlSchemaSet> пытается импортировать схему пространства имен `http://www.contoso.com`, загрузив ее по URL-адресу `http://www.contoso.com/schema.xsd`. В импортируемой схеме доступны только декларация схемы и типы, объявленные в документе схемы, даже если другие документы схемы из пространства имен `http://www.contoso.com` существуют в классе <xref:System.Xml.Schema.XmlSchemaSet>. Если файл `schema.xsd` не может быть обнаружен по URL-адресу `http://www.contoso.com/schema.xsd`, схема для пространства имен `http://www.contoso.com` не импортируется в импортируемую схему.  
  
## <a name="validating-xml-documents"></a>Проверка XML-документов  
 XML-документы могут быть проверены путем сопоставления со схемами в классе <xref:System.Xml.Schema.XmlSchemaSet>. Для проверки XML-документа нужно добавить схему в свойство <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> объекта <xref:System.Xml.XmlReaderSettings>, или добавить класс <xref:System.Xml.Schema.XmlSchemaSet> к свойству <xref:System.Xml.XmlReaderSettings.Schemas%2A> объекта <xref:System.Xml.XmlReaderSettings>. Затем объект <xref:System.Xml.XmlReaderSettings> используется методом <xref:System.Xml.XmlReader.Create%2A> класса <xref:System.Xml.XmlReader>, чтобы создать объект <xref:System.Xml.XmlReader> и проверить XML-документ.  
  
 Дополнительные сведения о проверке XML-документов с использованием класса <xref:System.Xml.Schema.XmlSchemaSet> см. в руководстве по [проверке схем XML (XSD) с помощью XmlSchemaSet](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemaset.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>
- [Использование XmlSchemaSet как кэша схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Проверка по XML-схеме (XSD) с помощью XmlSchemaSet](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemaset.md)
