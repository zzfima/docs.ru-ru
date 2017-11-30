---
title: "Использование класса XslCompiledTransform"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a5c71a7796790343bf39de5bbfd03997c25d5f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-xslcompiledtransform-class"></a>Использование класса XslCompiledTransform
Класс <xref:System.Xml.Xsl.XslCompiledTransform> является обработчиком XSLT в платформе Microsoft .NET Framework. Этот класс используется для компиляции таблиц стилей и выполнения преобразований XSLT.  
  
> [!NOTE]
>  Хотя класс <xref:System.Xml.Xsl.XslCompiledTransform> имеет более высокий общий уровень производительности, чем класс <xref:System.Xml.Xsl.XslTransform>, метод <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> класса <xref:System.Xml.Xsl.XslCompiledTransform> может выполняться медленнее, чем метод <xref:System.Xml.Xsl.XslTransform.Load%2A> класса <xref:System.Xml.Xsl.XslTransform> при первом вызове преобразования. Причина этого заключается в необходимости компиляции XSLT-файла перед его загрузкой. Дополнительные сведения см. в следующей записи блога: [XslCompiledTransform медленнее, чем XslTransform?](http://go.microsoft.com/fwlink/?LinkId=130590)  
  
## <a name="in-this-section"></a>Содержание  
 [Входные данные для класса XslCompiledTransform](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 Описываются доступные входные параметры XSLT.  
  
 [Параметры вывода в классе XslCompiledTransform](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 Описываются доступные выходные параметры XSLT.  
  
 [Разрешение внешних ресурсов во время обработки XSLT](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 Обсуждается использование класса <xref:System.Xml.XmlResolver> для разрешения внешних ресурсов.  
  
 [Расширение таблиц стилей XSLT](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 Обсуждается поддержка расширений XSLT.  
  
|||  
|-|-|  
|[Устранимые ошибки XSLT](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|Содержит список поведений по выбору, допустимых в соответствии с рекомендациями консорциума W3C по XSLT 1.0, и описывает, каким образом эти поведения обрабатываются классом <xref:System.Xml.Xsl.XslCompiledTransform>.|  
|[Как: преобразовать фрагмент узла](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|Описывает процесс преобразования фрагмента узла.|  
  
## <a name="related-sections"></a>Связанные разделы  
 [Миграция с класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 Обсуждается перенос кода из класса <xref:System.Xml.Xsl.XslTransform>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Xsl.XsltSettings>  
 <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
