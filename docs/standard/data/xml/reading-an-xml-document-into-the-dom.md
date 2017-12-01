---
title: "Считывание XML-документа в DOM"
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
ms.assetid: a4fb291f-5630-49ba-a49a-5b66c3b71e49
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b8844705b492574443ff4f37de33ccaf1f5fedd7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="reading-an-xml-document-into-the-dom"></a>Считывание XML-документа в DOM
XML-данные считываются в память из разных форматов. Они могут быть считаны из строки, URL-адреса, модуля чтения текста или класса, производного от класса <xref:System.Xml.XmlReader>.  
  
 Метод <xref:System.Xml.XmlDocument.Load%2A> загружает документ в память и имеет перегруженные методы для получения данных из разных форматов. Существует также метод <xref:System.Xml.XmlDocument.LoadXml%2A>, который считывает XML-данные из строки.  
  
 Разные методы <xref:System.Xml.XmlDocument.Load%2A> влияют на то, какие узлы создаются при загрузке модели DOM. В следующей таблице приведены различия между некоторыми методами <xref:System.Xml.XmlDocument.Load%2A>, а также ссылки на разделы, описывающие их.  
  
|Субъект|Раздел|  
|-------------|-----------|  
|Создание узлов пробелов|Объект, используемый для загрузки модели DOM, влияет на узлы пробелов и значащих пробелов, формируемые в модели DOM. Дополнительные сведения см. в разделе [пробелы обработка и значимых пробелов при загрузке модели DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).|  
|Загрузка XML-данных, начиная с определенного узла, или загрузка всего XML-документа|С помощью <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType> данных метода можно загрузить из отдельных узлов в модели DOM. Дополнительные сведения см. в разделе [загрузка данных из средства чтения](../../../../docs/standard/data/xml/load-data-from-a-reader.md).|  
|Проверка XML-данных по мере загрузки|Можно проводить проверку XML-данных, загружаемых в модель DOM, по мере их загрузки. Делается это с помощью проверяющего объекта <xref:System.Xml.XmlReader>. Дополнительные сведения о проверке XML при его загрузке см. в разделе [проверки XML-документа в DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md).|  
  
 В следующем примере показаны XML-данные, загружаемые с помощью метода <xref:System.Xml.XmlDocument.LoadXml%2A>, а также данные, которые затем сохраняются в текстовый файл `data.xml`.  
  
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
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
