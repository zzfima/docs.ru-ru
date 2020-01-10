---
title: XsltArgumentList для параметров таблицы стилей и объектов расширения
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: de2f0dce-6b98-4908-bba7-ed150cc50355
ms.openlocfilehash: 5cd733d557dabe66145fdbb848c473411d63c62b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709625"
---
# <a name="xsltargumentlist-for-style-sheet-parameters-and-extension-objects"></a>XsltArgumentList для параметров таблицы стилей и объектов расширения
Класс <xref:System.Xml.Xsl.XsltArgumentList> содержит параметры языка XSLT и объекты расширения XSLT. При передаче в метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> эти параметры и объекты расширения могут вызываться из таблиц стилей.  
  
> [!NOTE]
> Классы <xref:System.Xml.Xsl.XslTransform> и <xref:System.Xml.Xsl.XsltArgumentList> являются устаревшими в версии платформы NET Framework 2.0. Преобразования XSLT можно выполнять с помощью класса <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Класс <xref:System.Xml.Xsl.XsltArgumentList> содержит параметры XSLT и объекты расширения XSLT. При передаче в метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> эти параметры и объекты расширения могут вызываться из таблиц стилей.  
  
 Далее перечислены преимущества передачи объектов по сравнению с использованием внедренного скрипта.  
  
- Обеспечивает улучшенную инкапсуляцию и повторное использование классов.  
  
- Уменьшает размер и улучшает обслуживание таблиц стилей.  
  
- Поддерживает вызов методов из классов, принадлежащих пространствам имен, не определенным в наборе поддерживаемых пространств имен <xref:System>.  
  
- Поддерживает передачу фрагментов результирующего дерева в таблицу стилей с помощью <xref:System.Xml.XPath.XPathNodeIterator>.  
  
## <a name="xslt-style-sheet-parameters"></a>Параметры таблицы стилей XSLT  
 Параметры XSLT добавляются в <xref:System.Xml.Xsl.XsltArgumentList> с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>. В это время с объектом параметра связываются полное имя и URI-код пространства имен.  
  
 Объект параметра должен соответствовать типу W3C. В следующей таблице показано соответствие типов W3C и классов (типов) .NET Framework. Также показано, является ли тип W3C типом XPath или типом XSLT.  
  
|Тип W3C|Эквивалентный класс (тип) .NET Framework|Тип XPath или тип XSLT|  
|--------------|----------------------------------------------|-----------------------------|  
|Строка|System.String|XPath|  
|Логическое значение .|System.Boolean|XPath|  
|Числовой|System.Double|XPath|  
|Фрагмент дерева результатов|System.Xml.XPath.XPathNavigator|XSLT|  
|Набор узлов|System.Xml.XPath.XPathNodeIterator|XPath|  
  
 Если объект параметра не принадлежит ни к одному из классов выше, он принудительно преобразуется в тип Double или String. Типы Int16, UInt16, Int32, UInt32, Int64, UInt64, Single и Decimal преобразуются в Double. Все остальные типы преобразуются в тип String с помощью метода `ToString`.  
  
#### <a name="to-use-the-xslt-parameter-the-user-needs-to-do-the-following"></a>Чтобы использовать параметр XSLT, пользователь должен выполнить следующие действия.  
  
1. Создать объект <xref:System.Xml.Xsl.XsltArgumentList> и добавить объекты с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.  
  
2. Вызвать параметры из таблицы стилей.  
  
3. Передать <xref:System.Xml.Xsl.XsltArgumentList> методу <xref:System.Xml.Xsl.XslTransform.Transform%2A>.  
  
### <a name="example"></a>Пример  
 В следующем примере используется метод <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> для создания параметра, хранящего вычисленную дату скидки. Дата скидки вычисляется как 20 дней после даты заказа.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public class Sample  
  
   Private Const filename As String = "order.xml"  
   Private Const stylesheet As String = "discount.xsl"  
  
   Public Shared Sub Main()  
  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XsltArgumentList.  
    Dim xslArg As XsltArgumentList = New XsltArgumentList  
  
    'Calculate the discount date.  
    Dim today As DateTime = DateTime.Now  
    Dim d As DateTime = today.AddDays(20)  
    xslArg.AddParam("discount", "", d.ToString())  
  
    'Create an XmlTextWriter to handle the output.  
    Dim writer As XmlTextWriter = New XmlTextWriter("orderout.xml", Nothing)  
  
    'Transform the file.  
    xslt.Transform(doc, xslArg, writer, Nothing)  
  
    writer.Close()  
  
  End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample  
{  
   private const String filename = "order.xml";  
   private const String stylesheet = "discount.xsl";  
  
   public static void Main() {  
  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XsltArgumentList.  
    XsltArgumentList xslArg = new XsltArgumentList();  
  
    //Calculate the discount date.  
    DateTime today = DateTime.Now;  
    DateTime d = today.AddDays(20);  
    xslArg.AddParam("discount", "", d.ToString());  
  
    //Create an XmlTextWriter to handle the output.  
    XmlTextWriter writer = new XmlTextWriter("orderout.xml", null);  
  
    //Transform the file.  
    xslt.Transform(doc, xslArg, writer, null);  
    writer.Close();  
  }  
}  
```  
  
### <a name="input"></a>Input  
 order.xml  
  
```xml  
<!--Represents a customer order-->  
<order>  
  <book ISBN='10-861003-324'>  
    <title>The Handmaid's Tale</title>  
    <price>19.95</price>  
  </book>  
  <cd ISBN='2-3631-4'>  
    <title>Americana</title>  
    <price>16.95</price>  
  </cd>  
</order>  
```  
  
 discount.xsl  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">  
  <xsl:param name="discount"/>  
  <xsl:template match="/">  
    <order>  
      <xsl:variable name="sub-total" select="sum(//price)"/>  
      <total><xsl:value-of select="$sub-total"/></total>  
      15% discount if paid by: <xsl:value-of select="$discount"/>  
    </order>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
### <a name="output"></a>Вывод  
  
```xml  
<order>  
   <total>36.9</total>   
   15% discount if paid by: 5/6/2001 5:01:15 PM   
</order>  
```  
  
## <a name="xslt-extension-objects"></a>Объекты расширения XSLT  
 Объекты расширения XSLT добавляются в объект <xref:System.Xml.Xsl.XsltArgumentList> с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>. В это время с объектом расширения связываются полное имя и URI-код пространства имен.  
  
 Во время добавления объекта вызывающий объект метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> должен иметь полное доверие в политике безопасности. Если вызывающий объект обладает только частичным доверием, добавление объекта завершится ошибкой.  
  
 Объект добавляется успешно, однако не гарантируется успешность его выполнения. Во время вызова метода <xref:System.Xml.Xsl.XslTransform.Transform%2A> вычисляются разрешения по свидетельству, указанному во время вызова метода <xref:System.Xml.Xsl.XslTransform.Load%2A>, и этот набор разрешений назначается для всего процесса преобразования. Если объект расширения запускает действие, для которого необходимы разрешения, отсутствующие в наборе, вызывается исключение.  
  
 Объекты расширения возвращают один из четырех базовых типов данных XPath: number, string, Boolean и node set.  
  
#### <a name="to-use-the-xslt-extension-object-the-user-needs-to-do-the-following"></a>Чтобы использовать объект расширения XSLT, пользователь должен выполнить следующие действия  
  
1. Создать объект <xref:System.Xml.Xsl.XsltArgumentList> и добавить объект расширения с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.  
  
2. Вызвать объект расширения из таблицы стилей.  
  
3. Передать <xref:System.Xml.Xsl.XsltArgumentList> методу <xref:System.Xml.Xsl.XslTransform.Transform%2A>.  
  
### <a name="example"></a>Пример  
 В следующем примере вычисляется длина окружности по заданному радиусу.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
   Private Const filename As String = "number.xml"  
   Private Const stylesheet As String = "circle.xsl"  
  
   Public Shared Sub Main()  
        Dim test As Sample = New Sample  
   End Sub  
  
  Public Sub New()  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XsltArgumentList.  
    Dim xslArg As XsltArgumentList = New XsltArgumentList  
  
    'Add an object to calculate the circumference of the circle.  
    Dim obj As Calculate = New Calculate  
    xslArg.AddExtensionObject("urn:myObj", obj)  
  
    'Create an XmlTextWriter to output to the console.  
    Dim writer As XmlTextWriter = New XmlTextWriter(Console.Out)  
  
    'Transform the file.  
    xslt.Transform(doc, xslArg, writer, Nothing)  
    writer.Close()  
  
  End Sub  
  
  'Calculates the circumference of a circle given the radius.  
  Public Class Calculate  
  
    Private circ As double = 0  
  
    Public Function Circumference(radius As Double) As Double  
       circ = Math.PI*2*radius  
       Return circ  
    End Function  
  End Class  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample  
{  
   private const String filename = "number.xml";  
   private const String stylesheet = "circle.xsl";  
  
   public static void Main() {  
  
        Sample test = new Sample();  
    }  
  
  public Sample() {  
  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XsltArgumentList.  
    XsltArgumentList xslArg = new XsltArgumentList();  
  
    //Add an object to calculate the circumference of the circle.  
    Calculate obj = new Calculate();  
    xslArg.AddExtensionObject("urn:myObj", obj);  
  
    //Create an XmlTextWriter to output to the console.  
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
  
    //Transform the file.  
    xslt.Transform(doc, xslArg, writer, null);  
    writer.Close();  
  
  }  
  
  //Calculates the circumference of a circle given the radius.  
  public class Calculate {  
  
    private double circ = 0;  
  
    public double Circumference(double radius){  
       circ = Math.PI*2*radius;  
       return circ;  
    }  
  }  
}  
```  
  
### <a name="input"></a>Input  
 number.xml  
  
```xml  
<?xml version='1.0'?>  
<data>  
  <circle>  
    <radius>12</radius>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
  </circle>  
</data>    
```  
  
 circle.xsl  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
    xmlns:myObj="urn:myObj">  
  
  <xsl:template match="data">  
  <circles>  
  <xsl:for-each select="circle">  
    <circle>  
    <xsl:copy-of select="node()"/>  
       <circumference>  
          <xsl:value-of select="myObj:Circumference(radius)"/>          
       </circumference>  
    </circle>  
  </xsl:for-each>  
  </circles>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
### <a name="output"></a>Вывод  
 `<circles xmlns:myObj="urn:myObj">`  
  
 `<circle>`  
  
 `<radius>12</radius>`  
  
 `<circumference>75.398223686155</circumference>`  
  
 `</circle>`  
  
 `<circle>`  
  
 `<radius>37.5</radius>`  
  
 `<circumference>235.61944901923448</circumference>`  
  
 `</circle>`  
  
 `</circles>`  
  
## <a name="see-also"></a>См. также:

- [Реализация классом XslTransform XSLT-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
