---
title: "Грамматика XamlName | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DottedXamlName - грамматика [службы XAML]"
  - "грамматика [службы XAML], DottedXamlName"
  - "грамматика [службы XAML], XamlName"
  - "имена в языке XAML [службы XAML]"
  - "XamlName - грамматика [службы XAML]"
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
caps.latest.revision: 13
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 13
---
# Грамматика XamlName
Грамматика XamlName является определенной грамматикой, заданной в спецификации языка XAML \[MS\-XAML\], которая воспроизведена здесь для удобства.  
  
## Из спецификации XAML  
 Спецификация \[MS\-XAML\] определяет грамматику XamlName для определения набора разрешенных символьных идентификаторов, используемых для типов и свойств.  
  
 Строковые значения типа XamlName должны соответствовать следующей грамматике:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
  
```  
  
 которая допускает следующие общие значения категорий, определенных в базе знаков Юникод  
  
```  
  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 Язык XAML определяет вторую грамматику, DottedXamlName, которая используется для ссылок, определяемых свойством и событием, а также для вложенных членов.  Дополнительные сведения см. в разделах <xref:System.Windows.DependencyProperty> и [Общие сведения о языке XAML \(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
 Строковые значения типа DottedXamlName должны соответствовать следующей грамматике:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## Заметки  
 Полную спецификацию см. в разделе [\[MS\-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).