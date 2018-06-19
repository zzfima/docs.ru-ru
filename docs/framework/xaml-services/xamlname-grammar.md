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
ms.openlocfilehash: 32fd7b7b952ebbc853e41c0a8276d1ab487e619f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561895"
---
# <a name="xamlname-grammar"></a>Грамматика XamlName
Грамматика XamlName является определенной грамматикой, определенные в спецификации языка XAML [MS-XAML], которая воспроизводится здесь для удобства.  
  
## <a name="from-the-xaml-specification"></a>Из спецификации XAML  
 В спецификации [MS-XAML] определяет грамматику XamlName для определения набора разрешенных символьных идентификаторов, используемых для типов и свойств.  
  
 Строковые значения типа XamlName должны соответствовать следующей грамматике:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 Предполагается следующие общие значения категорий, как определено в базе данных символов Юникода  
  
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
  
 Код XAML определяет вторую грамматику, DottedXamlName, который используется для свойства и события ссылок на, а также для вложенных элементов. Дополнительные сведения см. в разделе <xref:System.Windows.DependencyProperty> и [Обзор XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
 Строковые значения типа DottedXamlName должны соответствовать следующей грамматике:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Примечания  
 Полную спецификацию в разделе [ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).
