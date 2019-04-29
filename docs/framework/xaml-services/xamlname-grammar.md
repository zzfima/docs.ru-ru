---
title: Грамматика XamlName
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: 642ca16142bdfe78a40ddf4e6a3a79ce6a8a4985
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938753"
---
# <a name="xamlname-grammar"></a>Грамматика XamlName
Грамматика XamlName является грамматики, который определен в спецификации языка XAML [MS-XAML], который здесь приведен для удобства.  
  
## <a name="from-the-xaml-specification"></a>Из спецификации XAML  
 В спецификации [MS-XAML] определяет Грамматика XamlName для определения набора разрешенных символьных идентификаторов, используемых для типов и свойств.  
  
 Строковые значения, которые имеют тип XamlName должны соответствовать следующей грамматике:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 Предполагает следующие значения общей категории, как определено в база данных символов Юникода  
  
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
  
 XAML определяет вторую грамматику, DottedXamlName, который используется для свойств и событий ссылок, а также для вложенных элементов. Дополнительные сведения см. в разделе <xref:System.Windows.DependencyProperty> и [Обзор XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md).  
  
 Строковые значения, которые относятся к типу, DottedXamlName должны соответствовать следующей грамматике:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Примечания  
 Полное же описание объекта, см. в разделе [ \[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).
