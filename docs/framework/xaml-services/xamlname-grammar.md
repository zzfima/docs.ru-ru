---
title: "Грамматика XamlName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47a2d72ea9558003412cc3773e26fb5be751fa19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="xamlname-grammar"></a><span data-ttu-id="97124-102">Грамматика XamlName</span><span class="sxs-lookup"><span data-stu-id="97124-102">XamlName Grammar</span></span>
<span data-ttu-id="97124-103">Грамматика XamlName является определенной грамматикой, определенные в спецификации языка XAML [MS-XAML], которая воспроизводится здесь для удобства.</span><span class="sxs-lookup"><span data-stu-id="97124-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="97124-104">Из спецификации XAML</span><span class="sxs-lookup"><span data-stu-id="97124-104">From the XAML Specification</span></span>  
 <span data-ttu-id="97124-105">В спецификации [MS-XAML] определяет грамматику XamlName для определения набора разрешенных символьных идентификаторов, используемых для типов и свойств.</span><span class="sxs-lookup"><span data-stu-id="97124-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="97124-106">Строковые значения типа XamlName должны соответствовать следующей грамматике:</span><span class="sxs-lookup"><span data-stu-id="97124-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="97124-107">Предполагается следующие общие значения категорий, как определено в базе данных символов Юникода</span><span class="sxs-lookup"><span data-stu-id="97124-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  
  
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
  
 <span data-ttu-id="97124-108">Код XAML определяет вторую грамматику, DottedXamlName, который используется для свойства и события ссылок на, а также для вложенных элементов.</span><span class="sxs-lookup"><span data-stu-id="97124-108">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="97124-109">Дополнительные сведения см. в разделе <xref:System.Windows.DependencyProperty> и [Обзор XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="97124-109">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="97124-110">Строковые значения типа DottedXamlName должны соответствовать следующей грамматике:</span><span class="sxs-lookup"><span data-stu-id="97124-110">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="97124-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="97124-111">Remarks</span></span>  
 <span data-ttu-id="97124-112">Полную спецификацию в разделе [ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="97124-112">For the complete specification, see [\[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
