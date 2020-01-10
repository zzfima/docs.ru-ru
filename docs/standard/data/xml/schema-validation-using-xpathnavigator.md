---
title: Проверка по схеме с помощью XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 81fa0e41-d9c9-46f0-b22b-50da839c77f5
ms.openlocfilehash: bfcbf7306e896af54808c49e25f95d0631f5bcc0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710210"
---
# <a name="schema-validation-using-xpathnavigator"></a>Проверка по схеме с помощью XPathNavigator
С помощью класса <xref:System.Xml.XmlDocument> можно проверять XML-содержимое в объекте <xref:System.Xml.XmlDocument> двумя способами. Первый способ проверки XML- содержимого заключается в использовании проверяющего объекта <xref:System.Xml.XmlReader>, а второй - в вызове метода <xref:System.Xml.XmlDocument.Validate%2A> класса <xref:System.Xml.XmlDocument>. Можно также выполнить проверку XML-содержимого «только для чтения» с помощью класса <xref:System.Xml.XPath.XPathDocument>.  
  
## <a name="validating-xml-data"></a>Проверка XML-данных  
 Класс <xref:System.Xml.XmlDocument> по умолчанию не выполняет проверку XML-документа с помощью определения DTD или XSD. Он только проверяет правильность формата XML-документа.  
  
 Первый способ проверки XML-документа заключается в его проверке при загрузке в объект <xref:System.Xml.XmlDocument> с помощью проверяющего объекта <xref:System.Xml.XmlReader>. Второй способ состоит в проверке ранее нетипизированного XML-документа с помощью метода <xref:System.Xml.XmlDocument.Validate%2A> класса <xref:System.Xml.XmlDocument>. В обоих случаях изменения в проверяемом XML-документе можно проверить повторно с помощью метода <xref:System.Xml.XmlDocument.Validate%2A> класса <xref:System.Xml.XmlDocument>.  
  
### <a name="validating-a-document-as-it-is-loaded"></a>Проверка документа при загрузке  
 Проверочный объект <xref:System.Xml.XmlReader> создается путем передачи объекта <xref:System.Xml.XmlReaderSettings> методу <xref:System.Xml.XmlReader.Create%2A> класса <xref:System.Xml.XmlReader>, который принимает объект <xref:System.Xml.XmlReaderSettings> в качестве параметра. Свойство <xref:System.Xml.XmlReaderSettings> объекта <xref:System.Xml.XmlReaderSettings.ValidationType%2A>, переданного в качестве параметра, имеет значение `Schema`, а схема XML для XML-документа, содержащегося в объекте <xref:System.Xml.XmlDocument>, добавляется к его свойству <xref:System.Xml.XmlReaderSettings.Schemas%2A>. После этого проверочный объект <xref:System.Xml.XmlReader> используется для создания объекта <xref:System.Xml.XmlDocument>.  
  
 В следующем примере выполняется проверка файла `contosoBooks.xml`, загруженного в объект <xref:System.Xml.XmlDocument> путем создания объекта <xref:System.Xml.XmlDocument> с помощью проверяющего объекта <xref:System.Xml.XmlReader>. Поскольку XML-документ допустим в соответствии со своей схемой, ошибки или предупреждения проверки не формируются.  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidatingReaderExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Try  
            Dim settings As XmlReaderSettings = New XmlReaderSettings()  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
            settings.ValidationType = ValidationType.Schema  
  
            Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
            Dim document As XmlDocument = New XmlDocument()  
            document.Load(reader)  
            Dim navigator As XPathNavigator = document.CreateNavigator()  
  
        Catch e As Exception  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message)  
        End Try  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidatingReaderExample  
{  
    static void Main(string[] args)  
    {  
        try  
        {  
            XmlReaderSettings settings = new XmlReaderSettings();  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
            settings.ValidationType = ValidationType.Schema;  
  
            XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
            XmlDocument document = new XmlDocument();  
            document.Load(reader);  
            XPathNavigator navigator = document.CreateNavigator();  
        }  
        catch (Exception e)  
        {  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message);  
        }  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 В примере в качестве входных данных используется файл `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 В примере также в качестве входных данных используется `contosoBooks.xsd`.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 В приведенном выше примере при вызове метода <xref:System.Xml.Schema.XmlSchemaValidationException> возникает исключение <xref:System.Xml.XmlDocument.Load%2A>, если какой-либо атрибут или тип элемента не соответствует типу, указанному в проверочной схеме. Если <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> установлен на проверяющий объект <xref:System.Xml.XmlReader>, метод <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> будет вызываться для каждого недопустимого типа.  
  
 Исключение <xref:System.Xml.Schema.XmlSchemaException> возникает, если объект <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> выполняет доступ к атрибуту или элементу, у которого свойство `invalid` имеет значение <xref:System.Xml.XPath.XPathNavigator>.  
  
 Свойство <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> можно использовать для определения допустимости отдельного атрибута или элемента при их оценке с помощью объекта <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
> Если XML-документ загружается в объект <xref:System.Xml.XmlDocument> со связанной схемой, определяющей значения по умолчанию, объект <xref:System.Xml.XmlDocument> рассматривает их как значения по умолчанию XML-документа. Это означает, что свойство <xref:System.Xml.XPath.XPathNavigator.IsEmptyElement%2A> всегда возвращает значение `false` для элемента, получившего значения по умолчанию из схемы, даже если в XML-документе это был пустой элемент.  
  
### <a name="validating-a-document-using-the-validate-method"></a>Проверка документа с помощью метода Validate  
 Метод <xref:System.Xml.XmlDocument.Validate%2A> класса <xref:System.Xml.XmlDocument> проверяет XML-документ, содержащийся в объекте <xref:System.Xml.XmlDocument>, по схеме, указанной в свойстве <xref:System.Xml.XmlDocument> объекта <xref:System.Xml.XmlDocument.Schemas%2A>, и выполняет приращение информационного набора. Результатом является замена в объекте <xref:System.Xml.XmlDocument> ранее нетипизированного XML-документа типизированным документом.  
  
 Объект <xref:System.Xml.XmlDocument> сообщает об ошибках и предупреждениях проверки схемы с помощью делегата <xref:System.Xml.Schema.ValidationEventHandler>, передаваемого в качестве параметра методу <xref:System.Xml.XmlDocument.Validate%2A>.  
  
 Следующий пример проверяет файл `contosoBooks.xml`, содержащийся в объекте <xref:System.Xml.XmlDocument> по схеме `contosoBooks.xsd`, содержащейся в свойстве <xref:System.Xml.XmlDocument> объекта <xref:System.Xml.XmlDocument.Schemas%2A>.  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidateExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Dim document As XmlDocument = New XmlDocument()  
        document.Load("contosoBooks.xml")  
        Dim navigator As XPathNavigator = document.CreateNavigator()  
  
        document.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
        Dim validation As ValidationEventHandler = New ValidationEventHandler(AddressOf SchemaValidationHandler)  
  
        document.Validate(validation)  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidateExample  
{  
    static void Main(string[] args)  
    {  
        XmlDocument document = new XmlDocument();  
        document.Load("contosoBooks.xml");  
        XPathNavigator navigator = document.CreateNavigator();  
  
        document.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
        ValidationEventHandler validation = new ValidationEventHandler(SchemaValidationHandler);  
  
        document.Validate(validation);  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 В примере в качестве входных данных используется файл `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 В примере также в качестве входных данных используется `contosoBooks.xsd`.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
### <a name="validating-modifications"></a>Проверка изменений  
 После внесения изменений в XML-документ можно проверить эти изменения по схеме XML-документа с помощью метода <xref:System.Xml.XmlDocument.Validate%2A> класса <xref:System.Xml.XmlDocument>.  
  
 В следующем примере выполняется проверка файла `contosoBooks.xml`, загруженного в объект <xref:System.Xml.XmlDocument> путем создания объекта <xref:System.Xml.XmlDocument> с помощью проверяющего объекта <xref:System.Xml.XmlReader>. XML-документ успешно проходит проверку во время загрузки без формирования ошибок и предупреждений проверки схемы. Затем пример выполняет два изменения в XML-документе, недопустимых по схеме `contosoBooks.xsd`. Первое изменение вставляет недопустимый дочерний элемент, что приводит к ошибке проверки схемы. Второе изменение присваивает значение типизированному узлу, недопустимое с точки зрения типа узла, что вызывает исключение.  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidatingReaderExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Try  
            Dim settings As XmlReaderSettings = New XmlReaderSettings()  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
            settings.ValidationType = ValidationType.Schema  
  
            Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
            Dim document As XmlDocument = New XmlDocument()  
            document.Load(reader)  
            Dim navigator As XPathNavigator = document.CreateNavigator()  
  
            Dim validation As ValidationEventHandler = New ValidationEventHandler(AddressOf SchemaValidationHandler)  
  
            navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
            navigator.MoveToChild("book", "http://www.contoso.com/books")  
            navigator.MoveToChild("author", "http://www.contoso.com/books")  
  
            navigator.AppendChild("<title>Book Title</title>")  
  
            document.Validate(validation)  
  
            navigator.MoveToParent()  
            navigator.MoveToChild("price", "http://www.contoso.com/books")  
            navigator.SetTypedValue(DateTime.Now)  
        Catch e As Exception  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message)  
        End Try  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidatingReaderExample  
{  
    static void Main(string[] args)  
    {  
        try  
        {  
            XmlReaderSettings settings = new XmlReaderSettings();  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
            settings.ValidationType = ValidationType.Schema;  
  
            XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
            XmlDocument document = new XmlDocument();  
            document.Load(reader);  
            XPathNavigator navigator = document.CreateNavigator();  
  
            ValidationEventHandler validation = new ValidationEventHandler(SchemaValidationHandler);  
  
            navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
            navigator.MoveToChild("book", "http://www.contoso.com/books");  
            navigator.MoveToChild("author", "http://www.contoso.com/books");  
  
            navigator.AppendChild("<title>Book Title</title>");  
  
            document.Validate(validation);  
  
            navigator.MoveToParent();  
            navigator.MoveToChild("price", "http://www.contoso.com/books");  
            navigator.SetTypedValue(DateTime.Now);  
        }  
        catch (Exception e)  
        {  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message);  
        }  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 В примере в качестве входных данных используется файл `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 В примере также в качестве входных данных используется `contosoBooks.xsd`.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 В приведенном выше примере в XML-документ, содержащийся в объекте <xref:System.Xml.XmlDocument>, вносятся два изменения. Во время загрузки этого XML-документа все ошибки проверки схемы будут обрабатываться методом обработчика события проверки и выводиться на консоль.  
  
 В этом примере ошибки проверки возникли после загрузки XML-документа и были обнаружены методом <xref:System.Xml.XmlDocument.Validate%2A> класса <xref:System.Xml.XmlDocument>.  
  
 Изменения, сделанные методом <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> класса <xref:System.Xml.XPath.XPathNavigator>, вызвали исключение <xref:System.InvalidCastException>, поскольку новое значение недопустимо с точки зрения типа схемы узла.  
  
 Дополнительные сведения об изменении значений с помощью метода <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> см. в руководстве по [изменению данных XML с помощью XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md).  
  
### <a name="read-only-validation"></a>Проверка «только для чтения»  
 Класс <xref:System.Xml.XPath.XPathDocument> является доступным только для чтения, хранящимся в памяти представлением XML-документа. Классы <xref:System.Xml.XPath.XPathDocument> и <xref:System.Xml.XmlDocument> создают объекты <xref:System.Xml.XPath.XPathNavigator> для перехода по XML-документам и их изменения. Поскольку класс <xref:System.Xml.XPath.XPathDocument> доступен только для чтения, объект <xref:System.Xml.XPath.XPathNavigator>, возвращенный из объекта <xref:System.Xml.XPath.XPathDocument>, не может изменять XML-документ, содержащийся в объекте <xref:System.Xml.XPath.XPathDocument>.  
  
 Для проверки можно создать объект <xref:System.Xml.XPath.XPathDocument> точно так же, как создается объект <xref:System.Xml.XmlDocument>, используя проверяющий объект <xref:System.Xml.XmlReader>, как описано выше в этом разделе. Объект <xref:System.Xml.XPath.XPathDocument> проверяет XML-документ во время загрузки, но, поскольку в объекте <xref:System.Xml.XPath.XPathDocument> нельзя изменять XML-данные, повторно проверить этот XML-документ невозможно.  
  
 Дополнительные сведения о доступных только для чтения и изменяемых объектах <xref:System.Xml.XPath.XPathNavigator> см. в руководстве по [чтению данных XML с помощью XPathDocument и XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Чтение XML-данных с помощью XPathDocument и XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)
- [Выбор, вычисление и отбор XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
- [Доступ к XML-данным с помощью класса XPathNavigator](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)
- [Изменение XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)
