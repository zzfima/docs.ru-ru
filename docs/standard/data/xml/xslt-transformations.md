---
title: "Преобразования XSLT | Microsoft Docs"
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
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# Преобразования XSLT
Язык XSLT позволяет преобразовать содержимое исходного XML\-документа в другой документ, отличный по формату или структуре.  Например, с помощью XSLT можно преобразовать XML в HTML для использования на веб\-узле или преобразовать в документ, в котором будут только поля, необходимые приложению.  Этот процесс преобразования определяется в [рекомендации W3C XSL Transformations \(XSLT\) Version 1.0](http://go.microsoft.com/fwlink/?LinkID=49919).  
  
 Класс <xref:System.Xml.Xsl.XslCompiledTransform> является обработчиком XSLT в платформе .NET Framework.  Класс <xref:System.Xml.Xsl.XslCompiledTransform> поддерживает рекомендации W3C XSLT 1.0.  
  
> [!NOTE]
>  Класс <xref:System.Xml.Xsl.XslTransform> в платформе .NET Framework версии 2.0 является устаревшим.  Класс <xref:System.Xml.Xsl.XslCompiledTransform> является новой реализацией обработчика XSLT.  Улучшена его производительность и добавлены новые средства безопасности.  XSLT\-приложения рекомендуется создавать с помощью класса <xref:System.Xml.Xsl.XslCompiledTransform>  
  
## В этом подразделе  
 [Использование класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)  
 Содержит сведения об использовании класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
 [Миграция с класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 Обсуждается перенос кода из класса <xref:System.Xml.Xsl.XslTransform>.  
  
 [XSLT\-компилятор \(xsltc.exe\)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)  
 Предоставляются сведения об использовании XSLT\-компилятора.  
  
 [XSLT\-преобразования с помощью класса XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 Содержит сведения об использовании класса <xref:System.Xml.Xsl.XslTransform>.  
  
 **Примечание** Класс <xref:System.Xml.Xsl.XslTransform> устарел в версии платформы .NET Framework 2.0.  
  
## Ссылка  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
  
 <xref:System.Xml.Xsl.XsltArgumentList>  
  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## Связанные подразделы  
 [XML\-документы и данные](../../../../docs/standard/data/xml/index.md)