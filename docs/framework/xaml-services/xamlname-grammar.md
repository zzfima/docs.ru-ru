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
# <a name="xamlname-grammar"></a><span data-ttu-id="42203-102">Грамматика XamlName</span><span class="sxs-lookup"><span data-stu-id="42203-102">XamlName Grammar</span></span>
<span data-ttu-id="42203-103">Грамматика XamlName является грамматики, который определен в спецификации языка XAML [MS-XAML], который здесь приведен для удобства.</span><span class="sxs-lookup"><span data-stu-id="42203-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="42203-104">Из спецификации XAML</span><span class="sxs-lookup"><span data-stu-id="42203-104">From the XAML Specification</span></span>  
 <span data-ttu-id="42203-105">В спецификации [MS-XAML] определяет Грамматика XamlName для определения набора разрешенных символьных идентификаторов, используемых для типов и свойств.</span><span class="sxs-lookup"><span data-stu-id="42203-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="42203-106">Строковые значения, которые имеют тип XamlName должны соответствовать следующей грамматике:</span><span class="sxs-lookup"><span data-stu-id="42203-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="42203-107">Предполагает следующие значения общей категории, как определено в база данных символов Юникода</span><span class="sxs-lookup"><span data-stu-id="42203-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  
  
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
  
 <span data-ttu-id="42203-108">XAML определяет вторую грамматику, DottedXamlName, который используется для свойств и событий ссылок, а также для вложенных элементов.</span><span class="sxs-lookup"><span data-stu-id="42203-108">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="42203-109">Дополнительные сведения см. в разделе <xref:System.Windows.DependencyProperty> и [Обзор XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="42203-109">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="42203-110">Строковые значения, которые относятся к типу, DottedXamlName должны соответствовать следующей грамматике:</span><span class="sxs-lookup"><span data-stu-id="42203-110">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="42203-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="42203-111">Remarks</span></span>  
 <span data-ttu-id="42203-112">Полное же описание объекта, см. в разделе [ \[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="42203-112">For the complete specification, see [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
