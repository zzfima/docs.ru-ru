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
ms.openlocfilehash: a1e7a5a03db4a24ed4d13d62899754cfe9e76b56
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837159"
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
| Младший номер                 | Буква: другие                 |
| Mn                 | Пометить, без промежутков             |
| Mc                 | Метка: комбинированная       |
| Nd                 | Число, десятичное               |
| Nl                 | Число: буква                |
 
 XAML определяет вторую грамматику, Доттедксамлнаме, которая используется для уточненных ссылок на свойства и события, а также для присоединенных членов. Дополнительные сведения см. в разделе <xref:System.Windows.DependencyProperty> и [Общие сведения о XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md).  
  
 Строковые значения типа Доттедксамлнаме должны соответствовать следующей грамматике:  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Заметки  
 Полную спецификацию см. в разделе [\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).
