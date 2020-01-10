---
title: Как выполнить XSLT-преобразование с помощью сборки
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 76ee440b-d134-4f8f-8262-b917ad6dcbf6
ms.openlocfilehash: 9fd8656594730f29d28cbfdd130d322bfc000614
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710834"
---
# <a name="how-to-perform-an-xslt-transformation-by-using-an-assembly"></a>Как выполнить XSLT-преобразование с помощью сборки
XSLT-компилятор (xsltc.exe) компилирует таблицы стилей XSLT и создает сборку. Сборку можно передать непосредственно методу <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>.  
  
### <a name="to-copy-the-xml-and-xslt-files-to-your-local-computer"></a>Копирование XML-файлов и XSLT-файлов на локальный компьютер  
  
- Скопируйте XSLT-файл на локальный компьютер и переименуйте его в Transform.xsl.  
  
    ```xml  
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
      xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
      xmlns:user="urn:my-scripts">  
      <msxsl:script language="C#" implements-prefix="user">  
        <![CDATA[  
      public string discount(string price){  
        char[] trimChars = { '$' };  
        //trim leading $, convert price to type double  
        double discount_value = Convert.ToDouble(price.TrimStart(trimChars));  
        //apply 10% discount and round appropriately  
        discount_value = .9*discount_value;  
        //convert value to decimal and format as currency  
        string discount_price = discount_value.ToString("C");  
        return discount_price;  
      }  
      ]]>  
      </msxsl:script>  
      <xsl:template match="catalog">  
        <html>  
          <head></head>  
          <body>  
            <table border="1">  
              <tr>  
                <th align="left">Title</th>  
                <th align="left">Author</th>  
                <th align="left">Genre</th>  
                <th align="left">Publish Date</th>  
                <th align="left">Price</th>  
              </tr>  
              <xsl:for-each select="book">  
                <tr>  
                  <td>  
                    <xsl:value-of select="title"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="author"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="genre"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="publish_date"/>  
                  </td>  
                  <xsl:choose>  
                    <xsl:when test="genre = 'Fantasy'">  
                      <td>  
                        <xsl:value-of select="user:discount(price)"/>  
                      </td>  
                    </xsl:when>  
                    <xsl:otherwise>  
                      <td>  
                        <xsl:value-of select="price"/>  
                      </td>  
                    </xsl:otherwise>  
                  </xsl:choose>  
                </tr>  
              </xsl:for-each>  
            </table>  
          </body>  
        </html>  
      </xsl:template>  
    </xsl:stylesheet>  
    ```  
  
- Скопируйте XML-файл на локальный компьютер и переименуйте его в `books.xml`.  
  
    ```xml  
    <?xml version="1.0"?>  
    <catalog>  
       <book id="bk101">  
          <author>Gambardella, Matthew</author>  
          <title>XML Developer's Guide</title>  
          <genre>Computer</genre>  
          <price>$44.95</price>  
          <publish_date>2000-10-01</publish_date>  
       </book>  
       <book id="bk102">  
          <author>Ralls, Kim</author>  
          <title>Midnight Rain</title>  
          <genre>Fantasy</genre>  
          <price>$5.95</price>  
          <publish_date>2000-12-16</publish_date>  
       </book>  
       <book id="bk103">  
          <author>Corets, Eva</author>  
          <title>Maeve Ascendant</title>  
          <genre>Fantasy</genre>  
          <price>$5.95</price>  
          <publish_date>2000-11-17</publish_date>  
       </book>  
       <book id="bk106">  
          <author>Randall, Cynthia</author>  
          <title>Lover Birds</title>  
          <genre>Romance</genre>  
          <price>$4.95</price>  
          <publish_date>2000-09-02</publish_date>  
       </book>  
       <book id="bk107">  
          <author>Thurman, Paula</author>  
          <title>Splish Splash</title>  
          <genre>Romance</genre>  
          <price>$4.95</price>  
          <publish_date>2000-11-02</publish_date>  
       </book>  
    </catalog>  
    ```  
  
### <a name="to-compile-the-style-sheet-with-the-script-enabled"></a>Компиляция таблицы стилей с поддержкой скриптов  
  
1. При выполнении следующей команды из командной строки создаются две сборки с именами `Transform.dll` и `Transform_Script1.dll` (это действие выполняется по умолчанию. Если не указано иное, имя класса и сборки по умолчанию совпадает с именем главной таблицы стилей):  
  
    ```console  
    xsltc /settings:script+ Transform.xsl  
    ```
  
    Следующая команда явно задает имя класса Transform:  
  
    ```console  
    xsltc /settings:script+ /class:Transform Transform.xsl  
    ```  
  
### <a name="to-include-the-compiled-assembly-as-a-reference-when-you-compile-your-code"></a>Включение скомпилированной сборки в виде ссылки во время компиляции кода  
  
1. Можно включить сборку в Visual Studio, добавив ссылку в обозревателе решений, или из командной строки.  
  
2. Если используется язык C#, введите в командной строке следующее:  
  
    ```console  
    csc myCode.cs /r:system.dll;system.xml.dll;Transform.dll  
    ```  
  
3. Если используется язык Visual Basic, введите в командной строке следующее:  
  
    ```console  
    vbc myCode.vb /r:system.dll;system.xml.dll;Transform.dll  
    ```  
  
### <a name="to-use-the-compiled-assembly-in-your-code"></a>Использование скомпилированной сборки в коде  
  
В следующем примере показано, как выполнить преобразование XSLT, используя скомпилированную таблицу стилей.  
  
[!code-csharp[XslTransform_XSLTC#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XslTransform_XSLTC/CS/XslTransform_XSLTC.cs#1)]
[!code-vb[XslTransform_XSLTC#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslTransform_XSLTC/VB/XslTransform_XSLTC.vb#1)]  
  
Чтобы создать динамическую ссылку на скомпилированную сборку, замените
  
```csharp  
xslt.Load(typeof(Transform));  
```  
  
С  
  
```csharp 
xslt.Load(System.Reflection.Assembly.Load("Transform").GetType("Transform"));  
``` 
  
в примере выше. Дополнительные сведения о методе Assembly. Load см. в разделе <xref:System.Reflection.Assembly.Load%2A>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.Xsl.XslCompiledTransform>
- [Компилятор XSLT (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)
- [Преобразования XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
- [Сборка из командной строки с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
