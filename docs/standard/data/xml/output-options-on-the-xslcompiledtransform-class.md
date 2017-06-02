---
title: "Параметры вывода в классе XslCompiledTransform | Microsoft Docs"
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
ms.assetid: 91ce8cba-386c-411e-bb38-0891a0393c0a
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# Параметры вывода в классе XslCompiledTransform
В этом разделе рассматриваются доступные параметры вывода XSLT.  Параметры вывода можно указать в таблице стилей или методе <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
## Элемент xsl:output  
 Элемент `xsl:output` указывает параметры вывода.  Тип вывода, указанный методом <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>, определяет поведение параметров `xsl:output`.  
  
 В следующей таблице описано поведение каждого атрибута, доступного в элементе `xsl:output`, если тип вывода \- поток или объект <xref:System.IO.TextWriter>.  
  
|Имя атрибута|Поведение|  
|------------------|---------------|  
|метод|Поддерживается.|  
|version|Не обрабатывается.  Версия всегда 1.0 для XML и 4.0 для HTML.|  
|encoding|Не учитывается при выводе в объект <xref:System.IO.TextWriter>.  Вместо него используется свойство <xref:System.IO.TextWriter.Encoding%2A?displayProperty=fullName>.|  
|omit\-xml\-declaration|Поддерживается.|  
|Автономный|Поддерживается.|  
|doctype\-public|Поддерживается.|  
|doctype\-system|Поддерживается.|  
|cdata\-section\-elements|Поддерживается.|  
|indent|Поддерживается.|  
|media\-type|Поддерживается.|  
  
#### Отправка выходных данных в XmlWriter  
 Если в таблице стилей используется элемент `xsl:output`, а тип вывода \- объект <xref:System.Xml.XmlWriter>, нужно использовать свойство <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=fullName> при создании объекта <xref:System.Xml.XmlWriter>.  Свойство <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=fullName> возвращает объект <xref:System.Xml.XmlWriterSettings>, который содержит сведения, полученные из элемента `xsl:output` скомпилированной таблицы стилей.  Этот объект <xref:System.Xml.XmlWriterSettings> можно передать в метод <xref:System.Xml.XmlWriter.Create%2A?displayProperty=fullName>, чтобы создать объект <xref:System.Xml.XmlWriter> с правильными настройками.  
  
## Типы вывода  
 В следующем списке описаны типы вывода, доступные в команде <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
#### XmlWriter  
 Класс <xref:System.Xml.XmlWriter> записывает потоки или файлы XML.  С помощью класса <xref:System.Xml.XmlWriterSettings> можно указать функции, поддерживающие объект <xref:System.Xml.XmlWriter>, включая параметры вывода.  Класс <xref:System.Xml.XmlWriter> представляет собой неотъемлемую часть платформы <xref:System.Xml>.  Используйте этот тип вывода для передачи выходных результатов в другой процесс XML.  
  
#### Строковое  
 Используйте этот тип вывода, чтобы указать URI выходного файла.  
  
#### Поток  
 Поток \- это абстракция последовательности байтов, например файла, устройства ввода\-вывода, межпроцессного канала связи или сокета TCP\/IP.  Класс <xref:System.IO.Stream> и его производные классы обеспечивают универсальное представление различных типов ввода и вывода, изолируя программиста от конкретных особенностей операционной системы и базовых устройств.  
  
 Используйте этот тип вывода для пересылки данных в объекты <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream> или выходной поток \(`Response.OutputStream`\).  
  
#### TextWriter  
 Объект <xref:System.IO.TextWriter> записывает последовательные символы.  Он реализован в классах <xref:System.IO.StringWriter> и <xref:System.IO.StreamWriter>, которые записывают символы в строки и потоки соответственно.  Используйте этот тип вывода, если нужно вывести строку.  
  
## Примечания  
  
-   При записи пустых тегов между последним символом имени элемента и обратной косой чертой записывается пробел, например `<myElement />`.  Это позволяет правильно отобразить сформированные HTML\-страницы в старых браузерах.  
  
## См. также  
 [Преобразования XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)