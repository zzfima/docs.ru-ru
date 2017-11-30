---
title: "Преобразования XSLT"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0d7fa8492487daff68fd8ebaf4159dd537d13e51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="xslt-transformations"></a>Преобразования XSLT
Язык XSLT позволяет преобразовать содержимое исходного XML-документа в другой документ, отличный по формату или структуре. Например, с помощью XSLT можно преобразовать XML в HTML для использования на веб-узле или преобразовать в документ, в котором будут только поля, необходимые приложению. Этот процесс преобразования определяется [преобразований XSL (XSLT) W3C версии 1.0](http://go.microsoft.com/fwlink/?LinkID=49919).  
  
 Класс <xref:System.Xml.Xsl.XslCompiledTransform> является обработчиком XSLT в платформе .NET Framework. Класс <xref:System.Xml.Xsl.XslCompiledTransform> поддерживает рекомендации W3C XSLT 1.0.  
  
> [!NOTE]
>  Класс <xref:System.Xml.Xsl.XslTransform> в платформе .NET Framework версии 2.0 является устаревшим. Класс <xref:System.Xml.Xsl.XslCompiledTransform> является новой реализацией обработчика XSLT. Улучшена его производительность и добавлены новые средства безопасности. XSLT-приложения рекомендуется создавать с помощью класса <xref:System.Xml.Xsl.XslCompiledTransform>  
  
## <a name="in-this-section"></a>Содержание  
 [Использование класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)  
 Содержит сведения об использовании класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
 [Миграция с класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 Обсуждается перенос кода из класса <xref:System.Xml.Xsl.XslTransform>.  
  
 [XSLT-компилятор (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)  
 Предоставляются сведения об использовании XSLT-компилятора.  
  
 [XSLT-преобразования с помощью класса XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 Содержит сведения об использовании класса <xref:System.Xml.Xsl.XslTransform>.  
  
 **Примечание** <xref:System.Xml.Xsl.XslTransform> класс не используется в версии .NET Framework 2.0.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
  
 <xref:System.Xml.Xsl.XsltArgumentList>  
  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## <a name="related-sections"></a>Связанные разделы  
 [XML-документы и данные](../../../../docs/standard/data/xml/index.md)
