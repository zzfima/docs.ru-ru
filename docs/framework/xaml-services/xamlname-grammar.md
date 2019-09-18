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
ms.openlocfilehash: 837a18ca18d0c634dfa5cc133aa013919cfb9d96
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053902"
---
# <a name="xamlname-grammar"></a>Грамматика XamlName
Грамматика Имяxaml — это специальная грамматика, определенная в спецификации языка XAML [MS-XAML], которая создается здесь для удобства.  
  
## <a name="from-the-xaml-specification"></a>Из спецификации XAML  
 Спецификация [MS-XAML] определяет грамматику Имяxaml для определения набора допустимых символьных идентификаторов, используемых для типов и свойств.  
  
 Строковые значения типа Имяxaml должны соответствовать следующей грамматике:  
  
```xaml  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 Предполагается, что следующие общие значения категории определены в базе данных символов Юникода.  

| Категория Юникода   | Описание                   |
|--------------------|-------------------------------|
| Lu                 | Буква: прописные буквы             |
| Ll                 | Буква: строчные буквы             |
| Lt                 | Буква: заглавный регистр             |
| Lm                 | Буква: модификатор              |
| Lo                 | Буква: другие                 |
| Mn                 | Пометить, без промежутков             |
| Mc                 | Метка: комбинированная       |
| Nd                 | Число, десятичное               |
| Nl                 | Число: буква                |
 
 XAML определяет вторую грамматику, Доттедксамлнаме, которая используется для уточненных ссылок на свойства и события, а также для присоединенных членов. Дополнительные сведения см. в <xref:System.Windows.DependencyProperty> разделе [Общие сведения о языке XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md).  
  
 Строковые значения типа Доттедксамлнаме должны соответствовать следующей грамматике:  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Примечания  
 Полную спецификацию см. в разделе [ \[MS-\]XAML](https://go.microsoft.com/fwlink/?LinkId=114525).
