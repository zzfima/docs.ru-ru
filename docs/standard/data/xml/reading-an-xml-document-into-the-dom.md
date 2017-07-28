---
title: "Считывание XML-документа в DOM | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: a4fb291f-5630-49ba-a49a-5b66c3b71e49
caps.latest.revision: 3
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# Считывание XML-документа в DOM
XML\-данные считываются в память из разных форматов.  Они могут быть считаны из строки, URL\-адреса, модуля чтения текста или класса, производного от класса <xref:System.Xml.XmlReader>.  
  
 Метод <xref:System.Xml.XmlDocument.Load%2A> загружает документ в память и имеет перегруженные методы для получения данных из разных форматов.  Существует также метод <xref:System.Xml.XmlDocument.LoadXml%2A>, который считывает XML\-данные из строки.  
  
 Разные методы <xref:System.Xml.XmlDocument.Load%2A> влияют на то, какие узлы создаются при загрузке модели DOM.  В следующей таблице приведены различия между некоторыми методами <xref:System.Xml.XmlDocument.Load%2A>, а также ссылки на разделы, описывающие их.  
  
|Субъект|Раздел|  
|-------------|------------|  
|Создание узлов пробелов|Объект, используемый для загрузки модели DOM, влияет на узлы пробелов и значащих пробелов, формируемые в модели DOM.  Для получения дополнительной информации см. [Обработка незначительных и значительных пробелов при загрузке DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).|  
|Загрузка XML\-данных, начиная с определенного узла, или загрузка всего XML\-документа|С помощью метода <xref:System.Xml.XmlDocument.Load%2A?displayProperty=fullName> данные в модель DOM можно загружать с определенного узла.  Для получения дополнительной информации см. [Загрузка данных из модуля чтения](../../../../docs/standard/data/xml/load-data-from-a-reader.md).|  
|Проверка XML\-данных по мере загрузки|Можно проводить проверку XML\-данных, загружаемых в модель DOM, по мере их загрузки.  Делается это с помощью проверяющего объекта <xref:System.Xml.XmlReader>.  Дополнительные сведения о проверке XML\-данных по мере их загрузки см. в разделе [Проверка XML\-документа в DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md).|  
  
 В следующем примере показаны XML\-данные, загружаемые с помощью метода <xref:System.Xml.XmlDocument.LoadXml%2A>, а также данные, которые затем сохраняются в текстовый файл `data.xml`.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.LoadXml(("<book genre='novel' ISBN='1-861001-57-5'>" & _  
                    "<title>Pride And Prejudice</title>" & _  
                    "</book>"))  
        ' Save the document to a file.  
        doc.Save("data.xml")  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    public static void Main()  
    {  
        // Create the XmlDocument.  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5'>" +  
                    "<title>Pride And Prejudice</title>" +  
                    "</book>");  
  
        // Save the document to a file.  
        doc.Save("data.xml");  
    }  
}  
```  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)