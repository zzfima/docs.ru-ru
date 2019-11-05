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
ms.openlocfilehash: a39d25f03583ab9020878b7a659bc99489231ff9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458882"
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
 
 XAML определяет вторую грамматику, Доттедксамлнаме, которая используется для уточненных ссылок на свойства и события, а также для присоединенных членов. Дополнительные сведения см. в разделе <xref:System.Windows.DependencyProperty> и [Общие сведения о XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md).  
  
 Строковые значения типа Доттедксамлнаме должны соответствовать следующей грамматике:  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Заметки  
 Полную спецификацию см. в разделе [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).
