---
title: "Сопоставление объектной иерархии с XML-данными"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 450e350b-6a68-4634-a2a5-33f4dc33baf0
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1bf43922fb702988e9057f541833cd58d33c820a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="mapping-the-object-hierarchy-to-xml-data"></a>Сопоставление объектной иерархии с XML-данными
Когда XML-документ находится в памяти, его концептуальным представлением является дерево. В распоряжении программиста имеется объектная иерархия для доступа к узлам этого дерева. Следующий пример показывает, как XML-содержимое становится узлами.  
  
 При считывании XML в модель DOM, его фрагменты преобразуются в узлы, и эти узлы сохраняют дополнительные метаданные о себе, в частности, тип узла и значения. Тип узла - это его объект и характеристики, определяющие выполняемые действия и свойства, которые можно установить и получить.  
  
 Если имеется следующий простой XML:  
  
 **Ввод**  
  
```xml  
<book>  
    <title>The Handmaid's Tale</title>  
</book>  
```  
  
 Входные данные представлены в памяти следующим деревом узлов с назначенным свойством типа узлов:  
  
 ![Пример узла дерева](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")  
Представление дерева узлов book и title  
  
 `book` Элемент становится **XmlElement** объект, следующий элемент `title`, также становится **XmlElement**, а элемент content становится **XmlText** объекта. Изучить **XmlElement** методы и свойства, методы и свойства отличаются от методов и свойств, доступных для **XmlText** объекта. Поэтому очень важно знать, какой тип узла получает XML, так как тип узла определяет действия, которые можно выполнить.  
  
 В следующих примерах выполняется считывание XML-данных и запись другого текста, в зависимости от типа узла. Используя следующий XML-файл данных в качестве входных данных, **items.xml**:  
  
 **Ввод**  
  
```xml  
<?xml version="1.0"?>  
<!-- This is a sample XML document -->  
<!DOCTYPE Items [<!ENTITY number "123">]>  
<Items>  
  <Item>Test with an entity: &number;</Item>  
  <Item>test with a child element <more/> stuff</Item>  
  <Item>test with a CDATA section <![CDATA[<456>]]> def</Item>  
  <Item>Test with a char entity: A</Item>  
  <!-- Fourteen chars in this element.-->  
  <Item>1234567890ABCD</Item>  
</Items>  
```  
  
 Следующий пример кода считывает **items.xml** и отображает сведения для каждого типа узла.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
    Private Const filename As String = "items.xml"  
  
    Public Shared Sub Main()  
  
        Dim reader As XmlTextReader = Nothing  
  
        Try  
            ' Load the reader with the data file and   
            'ignore all white space nodes.   
            reader = New XmlTextReader(filename)  
            reader.WhitespaceHandling = WhitespaceHandling.None  
  
            ' Parse the file and display each of the nodes.  
            While reader.Read()  
                Select Case reader.NodeType  
                    Case XmlNodeType.Element  
                        Console.Write("<{0}>", reader.Name)  
                    Case XmlNodeType.Text  
                        Console.Write(reader.Value)  
                    Case XmlNodeType.CDATA  
                        Console.Write("<![CDATA[{0}]]>", reader.Value)  
                    Case XmlNodeType.ProcessingInstruction  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value)  
                    Case XmlNodeType.Comment  
                        Console.Write("<!--{0}-->", reader.Value)  
                    Case XmlNodeType.XmlDeclaration  
                        Console.Write("<?xml version='1.0'?>")  
                    Case XmlNodeType.Document  
                    Case XmlNodeType.DocumentType  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value)  
                    Case XmlNodeType.EntityReference  
                        Console.Write(reader.Name)  
                    Case XmlNodeType.EndElement  
                        Console.Write("</{0}>", reader.Name)  
                End Select  
            End While  
  
        Finally  
            If Not (reader Is Nothing) Then  
                reader.Close()  
            End If  
        End Try  
    End Sub 'Main ' End class  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    private const String filename = "items.xml";  
  
    public static void Main()  
    {  
        XmlTextReader reader = null;  
  
        try  
        {  
            // Load the reader with the data file and ignore   
            // all white space nodes.  
            reader = new XmlTextReader(filename);  
            reader.WhitespaceHandling = WhitespaceHandling.None;  
  
            // Parse the file and display each of the nodes.  
            while (reader.Read())  
            {  
                switch (reader.NodeType)  
                {  
                    case XmlNodeType.Element:  
                        Console.Write("<{0}>", reader.Name);  
                        break;  
                    case XmlNodeType.Text:  
                        Console.Write(reader.Value);  
                        break;  
                    case XmlNodeType.CDATA:  
                        Console.Write("<![CDATA[{0}]]>", reader.Value);  
                        break;  
                    case XmlNodeType.ProcessingInstruction:  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.Comment:  
                        Console.Write("<!--{0}-->", reader.Value);  
                        break;  
                    case XmlNodeType.XmlDeclaration:  
                        Console.Write("<?xml version='1.0'?>");  
                        break;  
                    case XmlNodeType.Document:  
                        break;  
                    case XmlNodeType.DocumentType:  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.EntityReference:  
                        Console.Write(reader.Name);  
                        break;  
                    case XmlNodeType.EndElement:  
                        Console.Write("</{0}>", reader.Name);  
                        break;  
                }  
            }  
        }  
  
        finally  
        {  
            if (reader != null)  
                reader.Close();  
        }  
    }  
} // End class  
```  
  
 Вывод примера содержит сопоставление данных типам узлов.  
  
 **Вывод**  
  
```xml  
<?xml version='1.0'?><!--This is a sample XML document --><!DOCTYPE Items [<!ENTITY number "123">]<Items><Item>Test with an entity: 123</Item><Item>test with a child element <more> stuff</Item><Item>test with a CDATA section <![CDATA[<456>]]> def</Item><Item>Test with a char entity: A</Item><--Fourteen chars in this element.--><Item>1234567890ABCD</Item></Items>  
```  
  
 Рассматривая входные данные построчно и используя выход, сформированный кодом, можно использовать следующую таблицу для анализа того, какой узел сформировал конкретные строки результата, и понять, какие XML-данные стали соответствующими типами узлов.  
  
|Ввод|Вывод|Проверка типа узла|  
|-----------|------------|--------------------|  
|\<? версия xml = «1.0»? >|\<? версия xml = "1.0"? >|XmlNodeType.XmlDeclaration|  
|\<!--Это образец XML-документа-->|\<!--Это образец XML-документа-->|XmlNodeType.Comment|  
|\<! Элементы DOCTYPE [\<! СУЩНОСТИ номер «123» >] >|\<! Элементы DOCTYPE [\<! СУЩНОСТИ номер «123» >]|XmlNodeType.DocumentType|  
|\<Элементы >|\<Элементы >|XmlNodeType.Element|  
|\<Item>|\<Item>|XmlNodeType.Element|  
|Тестирование с помощью сущности:&number;|Test with an entity: 123|XmlNodeType.Text|  
|\</ Элемент >|\</ Элемент >|XmlNodeType.EndElement|  
|\<Item>|\<Item>|XmNodeType.Element|  
|test with a child element|test with a child element|XmlNodeType.Text|  
|\<Дополнительные >|\<Дополнительные >|XmlNodeType.Element|  
|stuff|stuff|XmlNodeType.Text|  
|\</ Элемент >|\</ Элемент >|XmlNodeType.EndElement|  
|\<Item>|\<Item>|XmlNodeType.Element|  
|test with a CDATA section|test with a CDATA section|XmlTest.Text|  
|<! [CDATA [\<456 >]]\>|<! [CDATA [\<456 >]]\>|XmlTest.CDATA|  
|def|def|XmlNodeType.Text|  
|\</ Элемент >|\</ Элемент >|XmlNodeType.EndElement|  
|\<Item>|\<Item>|XmlNodeType.Element|  
|Тест с помощью сущности char: &\#65;|Test with a char entity: A|XmlNodeType.Text|  
|\</ Элемент >|\</ Элемент >|XmlNodeType.EndElement|  
|\<!--В этом элементе 14 типов данных char.-->|\<— В этом элементе 14 типов данных char.-->|XmlNodeType.Comment|  
|\<Item>|\<Item>|XmlNodeType.Element|  
|1234567890ABCD|1234567890ABCD|XmlNodeType.Text|  
|\</ Элемент >|\</ Элемент >|XmlNodeType.EndElement|  
|\</ Items >|\</ Items >|XmlNodeType.EndElement|  
  
 Необходимо знать, какой тип узла назначен, так как от типа узла зависят допустимые типы действий и типы свойств, которые можно установить и получить.  
  
 Управляет созданием узлов для пробелов при загрузке данных в модель DOM осуществляется **PreserveWhitespace** флаг. Дополнительные сведения см. в разделе [пробелы обработка и значимых пробелов при загрузке модели DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).  
  
 Чтобы добавить новые узлы в модель DOM, в разделе [Вставка узлов в XML-документ](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md). Удаление узлов из DOM, в разделе [удаление узлов, содержимого и значений из XML-документа](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md). Чтобы изменить содержимое узлов в модели DOM, в разделе [изменение узлов, содержимого и значений в XML-документ](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
