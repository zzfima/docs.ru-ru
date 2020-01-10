---
title: Разрешение внешних таблиц стилей XSLT и документов
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 920cfe3b-d525-4bb2-abf6-9431651f9cf9
ms.openlocfilehash: 504519532d9a6988209cf04fd6b6196796f929f8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710301"
---
# <a name="resolving-external-xslt-style-sheets-and-documents"></a>Разрешение внешних таблиц стилей XSLT и документов
В некоторых случаях в процессе преобразования может потребоваться разрешение внешних ресурсов.  
  
> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
 В некоторых случаях в процессе преобразования может потребоваться разрешение внешних ресурсов.  
  
- При использовании метода <xref:System.Xml.Xsl.XslTransform.Load%2A>, чтобы обнаружить внешнюю таблицу стилей.  
  
- При использовании метода <xref:System.Xml.Xsl.XslTransform.Load%2A>, чтобы разрешить любые элементы `<xsl:include>` или `<xsl:import>`, обнаруженные в таблице стилей.  
  
- При использовании метода <xref:System.Xml.Xsl.XslTransform.Transform%2A>, чтобы разрешить любые функции `document()`.  
  
## <a name="using-the-xmlresolver-class"></a>Использование класса XmlResolver  
 Если для проверки подлинности требуется доступ к сетевому ресурсу, используйте методы <xref:System.Xml.Xsl.XslTransform.Load%2A> с параметром <xref:System.Xml.XmlResolver>, чтобы передать объект <xref:System.Xml.XmlResolver> с набором необходимых свойств учетных данных.  
  
 Если нужно использовать специальный класс <xref:System.Xml.XmlResolver> или указать другие учетные данные, то в следующей таблице приведен список необходимых задач, в зависимости от того, когда необходимо разрешить внешний ресурс.  
  
|Процесс, требующий разрешения|Необходимая задача|  
|--------------------------------------|-------------------|  
|При использовании метода <xref:System.Xml.Xsl.XslTransform.Load%2A>, чтобы обнаружить таблицу стилей.|Указать перегруженный метод <xref:System.Xml.Xsl.XslTransform.Load%2A>, который принимает в качестве параметра объект <xref:System.Xml.XmlResolver>, если таблица стилей находится в ресурсе, требующем учетных данных.|  
|При использовании метода <xref:System.Xml.Xsl.XslTransform.Load%2A>, чтобы разрешить элементы `<xsl:include>` или `<xsl:import>`.|Указать перегруженный метод <xref:System.Xml.Xsl.XslTransform.Load%2A>, который принимает в качестве параметра объект <xref:System.Xml.XmlResolver>. Объект <xref:System.Xml.XmlResolver> используется для загрузки таблиц стилей, на которые ссылаются инструкции `import` или `include`. Если передается значение `null`, то внешние ресурсы не разрешаются.|  
|При использовании преобразования для разрешения любых функций `document()`.|Укажите объект <xref:System.Xml.XmlResolver> при преобразовании с помощью метода <xref:System.Xml.Xsl.XslTransform.Transform%2A>, который принимает аргумент <xref:System.Xml.XmlResolver>.|  
  
 Функция `document()` получает другие XML-ресурсы из таблицы стилей, в дополнение к начальным XML-данным, предоставленным входным потоком. Поскольку эта функция обеспечивает включение XML-данных, расположенных в других местах, объект <xref:System.Xml.XmlResolver> со значением `null`, предоставленный методу <xref:System.Xml.Xsl.XslTransform.Transform%2A>, предотвращает выполнение функции `document()`. Если необходимо использовать функцию `document()`, используйте метод <xref:System.Xml.Xsl.XslTransform.Transform%2A>, который получает объект <xref:System.Xml.XmlResolver> в качестве параметра, в дополнение к соответствующему набору разрешений.  
  
 Дополнительные сведения о методе <xref:System.Xml.Xsl.XslTransform.Load%2A> и использовании им класса <xref:System.Xml.XmlResolver> см. в разделе <xref:System.Xml.Xsl.XslTransform.Load%28System.String%2CSystem.Xml.XmlResolver%29?displayProperty=nameWithType>.  
  
 При вызове метода <xref:System.Xml.Xsl.XslTransform.Transform%2A> разрешения вычисляются с учетом свидетельств, предоставленных во время загрузки, и этот набор разрешений назначается всему процессу преобразования. Если функция `document()` пытается инициировать действие, для которого требуются разрешения, отсутствующие в наборе, вызывается исключение.  
  
## <a name="see-also"></a>См. также:

- [XSLT-преобразования с помощью класса XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [Реализация классом XslTransform XSLT-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
- [Результаты вывода XslTransform](../../../../docs/standard/data/xml/outputs-from-an-xsltransform.md)
- [XSLT-преобразования над различными хранилищами](../../../../docs/standard/data/xml/xslt-transformations-over-different-stores.md)
- [XsltArgumentList для параметров таблицы стилей и объектов расширения](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md)
- [Создание скриптов таблиц стилей XSLT с помощью \<msxsl:script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md)
- [Поддержка функции msxsl:node-set()](../../../../docs/standard/data/xml/support-for-the-msxsl-node-set-function.md)
- [XPathNavigator в преобразованиях](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [XPathNodeIterator в преобразованиях](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [Ввод XPathDocument в XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [Ввод XmlDataDocument в XslTransform](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
- [Ввод XmlDocument в XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
