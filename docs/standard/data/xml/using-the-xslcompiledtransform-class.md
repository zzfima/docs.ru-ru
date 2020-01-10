---
title: Использование класса XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
ms.openlocfilehash: 8212e37171ce693ee5624541f7886ef33a33b1da
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710054"
---
# <a name="using-the-xslcompiledtransform-class"></a>Использование класса XslCompiledTransform
Класс <xref:System.Xml.Xsl.XslCompiledTransform> является обработчиком XSLT в платформе Microsoft .NET Framework. Этот класс используется для компиляции таблиц стилей и выполнения преобразований XSLT.  
  
> [!NOTE]
> Хотя класс <xref:System.Xml.Xsl.XslCompiledTransform> имеет более высокий общий уровень производительности, чем класс <xref:System.Xml.Xsl.XslTransform>, метод <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> класса <xref:System.Xml.Xsl.XslCompiledTransform> может выполняться медленнее, чем метод <xref:System.Xml.Xsl.XslTransform.Load%2A> класса <xref:System.Xml.Xsl.XslTransform> при первом вызове преобразования. Причина этого заключается в необходимости компиляции XSLT-файла перед его загрузкой. См. дополнительные сведения о [сравнении XslCompiledTransform и XslTransform](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/)  
  
## <a name="in-this-section"></a>В этом разделе  
 [Входные данные для класса XslCompiledTransform](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 Описываются доступные входные параметры XSLT.  
  
 [Параметры вывода в классе XslCompiledTransform](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 Описываются доступные выходные параметры XSLT.  
  
 [Разрешение внешних ресурсов в ходе обработки XSLT](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 Обсуждается использование класса <xref:System.Xml.XmlResolver> для разрешения внешних ресурсов.  
  
 [Расширение таблиц стилей XSLT](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 Обсуждается поддержка расширений XSLT.  
  
|||  
|-|-|  
|[Устранимые ошибки XSLT](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|Содержит список поведений по выбору, допустимых в соответствии с рекомендациями консорциума W3C по XSLT 1.0, и описывает, каким образом эти поведения обрабатываются классом <xref:System.Xml.Xsl.XslCompiledTransform>.|  
|[Как преобразовать фрагмент узла](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|Описывает процесс преобразования фрагмента узла.|  
  
## <a name="related-sections"></a>Связанные разделы  
 [Миграция с класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 Обсуждается перенос кода из класса <xref:System.Xml.Xsl.XslTransform>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
