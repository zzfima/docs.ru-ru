---
title: Создание скриптов таблиц стилей XSLT с помощью <msxsl:script>
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 60e2541b-0cea-4b2e-a4fa-85f4c50f1bef
ms.openlocfilehash: 9bf57e0f74a353fb6512a24214e9479c1d813aab
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160213"
---
# <a name="xslt-stylesheet-scripting-using-msxslscript"></a>Создание скриптов таблиц стилей XSLT с помощью \<msxsl:script>
Класс <xref:System.Xml.Xsl.XslTransform> поддерживает внедрение скриптов с помощью элемента `script`.  
  
> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Класс <xref:System.Xml.Xsl.XslTransform> поддерживает внедрение скриптов с помощью элемента `script`. При загрузке таблицы стилей любые определенные функции компилируются на язык MSIL путем помещения в определение класса и в результате не имеют потерь производительности.  
  
 Элемент `<msxsl:script>` определен ниже:  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 , где `msxsl` является префиксом, привязанным к пространству имен `urn:schemas-microsoft-com:xslt`.  
  
 Атрибут `language` не является обязательным, но если он указан, его значение должно быть одним из следующих: `C#`, `VB`, `JScript`, `JavaScript`, `VisualBasic`или `CSharp`. Если не указан, значение по умолчанию - JScript. Атрибут `language-name` нечувствителен к регистру, так что значения «JavaScript» и «javascript» не различаются.  
  
 Атрибут `implements-prefix` обязателен. Этот атрибут используется для объявления пространства имен и связывания его с блоком скрипта. Значением этого атрибута является префикс, соответствующий пространству имен. Пространство имен может быть определено где-то в таблице стилей.  
  
 Так как элемент `msxsl:script` принадлежит пространству имен `urn:schemas-microsoft-com:xslt`, таблица стилей должна включать в себя декларацию пространства имен `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.  
  
 Если вызывающий скрипт не имеет разрешения доступа <xref:System.Security.Permissions.SecurityPermissionFlag>, скрипт в таблице стилей никогда не будет скомпилирован и при вызове метода <xref:System.Xml.Xsl.XslTransform.Load%2A> произойдет ошибка.  
  
 Если вызывающий имеет разрешение доступа `UnmanagedCode`, скрипт компилируется, но разрешенные операции зависят от свидетельства, которое указывается во время загрузки.  
  
 При использовании одного из методов <xref:System.Xml.Xsl.XslTransform.Load%2A>, которые принимают объект <xref:System.Xml.XmlReader> или объект <xref:System.Xml.XPath.XPathNavigator> для загрузки таблицы стилей, необходимо использовать перегрузку метода <xref:System.Xml.Xsl.XslTransform.Load%2A>, который принимает параметр <xref:System.Security.Policy.Evidence> как один из аргументов. Чтобы получить свидетельство, вызывающий должен иметь разрешение <xref:System.Security.Permissions.SecurityPermissionFlag>, чтобы предоставить `Evidence` сборке скрипта. Если вызывающий не имеет данного разрешения, то он может задать для параметра `Evidence` значение `null`. Это приводит к ошибке при вызове функции <xref:System.Xml.Xsl.XslTransform.Load%2A>, если функция находит скрипт. Разрешение `ControlEvidence` считается очень важным разрешением, которое должно предоставляться только коду с высокой степенью доверия.  
  
 Чтобы получить свидетельство из сборки используется метод `this.GetType().Assembly.Evidence`. Чтобы получить свидетельство из универсального идентификатора ресурсов (URI) используется метод `Evidence e = XmlSecureResolver.CreateEvidenceForUrl(stylesheetURI)`.  
  
 При использовании методов <xref:System.Xml.Xsl.XslTransform.Load%2A>, которые принимают объект <xref:System.Xml.XmlResolver>, но не объект `Evidence`, зона безопасности для сборки имеет по умолчанию полный уровень доверия. Дополнительные сведения см. в статьях <xref:System.Security.SecurityZone> и [Именованные наборы разрешений](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).  
  
 Функции можно объявлять внутри элемента `msxsl:script`. В следующей таблице показаны пространства имен, поддерживаемые по умолчанию. Можно использовать классы вне перечисленных пространств имен. Однако эти классы должны указываться полными именами.  
  
|Пространства имен по умолчанию|Description|  
|------------------------|-----------------|  
|Система|Системный класс.|  
|System.Collection|Классы коллекций.|  
|System.Text|Классы текста.|  
|System.Text.RegularExpressions|Классы регулярных выражений.|  
|System.Xml|Основные классы XML.|  
|System.Xml.Xsl;|Классы XSLT.|  
|System.Xml.XPath|Классы языка XPath.|  
|Microsoft.VisualBasic|Классы для скриптов Microsoft Visual Basic.|  
  
 При объявлении функции она заключается в блок скрипта. Таблицы стилей могут содержать несколько блоков скриптов, каждый из которых работает независимо от других. Это значит, что в одном блоке скрипта нельзя вызвать функцию, определенную в другом блоке, если в них не объявлены одно и то же пространство имен и один и тот же язык скрипта. Так как каждый блок скрипта может быть написан на своем языке, и блок анализируется в соответствии с грамматическими правилами средств синтаксического анализа языка, необходимо соблюдать правильный синтаксис используемого языка. Например, в блоке скрипта C# будет ошибкой использовать узлы комментариев XML `<!-- an XML comment -->`.  
  
 Указанные аргументы и возвращаемые значения, определенные функциями скрипта, должны представлять собой один из типов XPath консорциума W3C или XSLT. В следующей таблице приведены соответствующие типы W3C, эквивалентные классы (или типы) платформы .NET Framework, а также показано, является ли тип W3C типом XPath или типом XSLT.  
  
|Тип|Эквивалентный класс (или тип) .NET Framework|Тип XPath или тип XSLT|  
|----------|----------------------------------------------|-----------------------------|  
|String|System.String|XPath|  
|Логическое|System.Boolean|XPath|  
|Number|System.Double|XPath|  
|Фрагмент дерева результатов|System.Xml.XPath.XPathNavigator|XSLT|  
|Набор узлов|System.Xml.XPath.XPathNodeIterator|XPath|  
  
 Если функция скрипта использует один из числовых типов (Int16, UInt16, Int32, UInt32, Int64, UInt64, Single или Decimal), то он приводится к типу Double, который сопоставлен с числовым типом W3C XPath. Все другие типы принудительно приводятся к типу string с помощью метода `ToString`.  
  
 Если функция скрипта использует тип, отличный от перечисленных выше, или функция не компилируется при загрузке таблицы стилей в объект <xref:System.Xml.Xsl.XslTransform>, возникает исключение.  
  
 При использовании элемента `msxsl:script` мы настоятельно рекомендуем размещать скрипт, независимо от языка, в раздел CDATA. Например, следующий код XML показывает шаблон раздела CDATA, куда помещается код пользователя.  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    <![CDATA[  
    ... your code here ...  
    ]]>  
</msxsl:script>  
```  
  
 Настоятельно рекомендуется помещать все содержимое скрипта в секцию CDATA, так как операторы, идентификаторы или разделители для данного языка могут быть ошибочно интерпретированы как XML. В следующем примере показано, как использовать логический оператор AND в скрипт.  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    public string book(string abc, string xyz)  
    {  
        if ((abc == bar) && (abc == xyz)) return bar + xyz;  
        else return null;  
    }  
</msxsl:script>  
```  
  
 Этот код вызывает исключение, так как амперсанды не экранированы. Документ загружается как XML, и к тексту между тегами элемента `msxsl:script` не применяется никакая специальная обработка.  
  
## <a name="example"></a>Пример  
 В следующем примере используется внедренный скрипт для вычисления длины окружности по заданному радиусу.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
  
   Private Const filename As String = "number.xml"  
   Private Const stylesheet As String = "calc.xsl"  
  
   Public Shared Sub Main()  
  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XmlTextWriter to output to the console.
    Dim writer As XmlTextWriter = New XmlTextWriter(Console.Out)  
    writer.Formatting = Formatting.Indented  
  
    'Transform the file.  
    xslt.Transform(doc, Nothing, writer, Nothing)  
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
   private const String filename = "number.xml";  
   private const String stylesheet = "calc.xsl";  
  
   public static void Main()  
   {  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XmlTextWriter to output to the console.
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
    writer.Formatting = Formatting.Indented;  
  
    //Transform the file.  
    xslt.Transform(doc, null, writer, null);  
    writer.Close();  
  }  
}  
```  
  
## <a name="input"></a>Входные данные  
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
  
 calc.xsl  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
    xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
    xmlns:user="urn:my-scripts">  
  
  <msxsl:script language="C#" implements-prefix="user">  
     <![CDATA[  
     public double circumference(double radius)  
     {  
       double pi = 3.14;  
       double circ = pi*radius*2;  
       return circ;  
     }  
      ]]>  
   </msxsl:script>  
  
  <xsl:template match="data">
  <circles>  
  
  <xsl:for-each select="circle">  
    <circle>  
    <xsl:copy-of select="node()"/>  
       <circumference>  
          <xsl:value-of select="user:circumference(radius)"/>
       </circumference>  
    </circle>  
  </xsl:for-each>  
  </circles>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a>Выходные данные  
  
```xml  
<circles xmlns:msxsl="urn:schemas-microsoft-com:xslt" xmlns:user="urn:my-scripts">  
  <circle>  
    <radius>12</radius>  
    <circumference>75.36</circumference>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
    <circumference>235.5</circumference>  
  </circle>  
</circles>
```  
  
## <a name="see-also"></a>См. также раздел

- [Реализация классом XslTransform XSLT-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
