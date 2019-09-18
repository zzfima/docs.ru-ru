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
# <a name="xamlname-grammar"></a><span data-ttu-id="37a30-102">Грамматика XamlName</span><span class="sxs-lookup"><span data-stu-id="37a30-102">XamlName Grammar</span></span>
<span data-ttu-id="37a30-103">Грамматика Имяxaml — это специальная грамматика, определенная в спецификации языка XAML [MS-XAML], которая создается здесь для удобства.</span><span class="sxs-lookup"><span data-stu-id="37a30-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="37a30-104">Из спецификации XAML</span><span class="sxs-lookup"><span data-stu-id="37a30-104">From the XAML Specification</span></span>  
 <span data-ttu-id="37a30-105">Спецификация [MS-XAML] определяет грамматику Имяxaml для определения набора допустимых символьных идентификаторов, используемых для типов и свойств.</span><span class="sxs-lookup"><span data-stu-id="37a30-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="37a30-106">Строковые значения типа Имяxaml должны соответствовать следующей грамматике:</span><span class="sxs-lookup"><span data-stu-id="37a30-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```xaml  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="37a30-107">Предполагается, что следующие общие значения категории определены в базе данных символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="37a30-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  

| <span data-ttu-id="37a30-108">Категория Юникода</span><span class="sxs-lookup"><span data-stu-id="37a30-108">Unicode category</span></span>   | <span data-ttu-id="37a30-109">Описание</span><span class="sxs-lookup"><span data-stu-id="37a30-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="37a30-110">Lu</span><span class="sxs-lookup"><span data-stu-id="37a30-110">Lu</span></span>                 | <span data-ttu-id="37a30-111">Буква: прописные буквы</span><span class="sxs-lookup"><span data-stu-id="37a30-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="37a30-112">Ll</span><span class="sxs-lookup"><span data-stu-id="37a30-112">Ll</span></span>                 | <span data-ttu-id="37a30-113">Буква: строчные буквы</span><span class="sxs-lookup"><span data-stu-id="37a30-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="37a30-114">Lt</span><span class="sxs-lookup"><span data-stu-id="37a30-114">Lt</span></span>                 | <span data-ttu-id="37a30-115">Буква: заглавный регистр</span><span class="sxs-lookup"><span data-stu-id="37a30-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="37a30-116">Lm</span><span class="sxs-lookup"><span data-stu-id="37a30-116">Lm</span></span>                 | <span data-ttu-id="37a30-117">Буква: модификатор</span><span class="sxs-lookup"><span data-stu-id="37a30-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="37a30-118">Lo</span><span class="sxs-lookup"><span data-stu-id="37a30-118">Lo</span></span>                 | <span data-ttu-id="37a30-119">Буква: другие</span><span class="sxs-lookup"><span data-stu-id="37a30-119">Letter, Other</span></span>                 |
| <span data-ttu-id="37a30-120">Mn</span><span class="sxs-lookup"><span data-stu-id="37a30-120">Mn</span></span>                 | <span data-ttu-id="37a30-121">Пометить, без промежутков</span><span class="sxs-lookup"><span data-stu-id="37a30-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="37a30-122">Mc</span><span class="sxs-lookup"><span data-stu-id="37a30-122">Mc</span></span>                 | <span data-ttu-id="37a30-123">Метка: комбинированная</span><span class="sxs-lookup"><span data-stu-id="37a30-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="37a30-124">Nd</span><span class="sxs-lookup"><span data-stu-id="37a30-124">Nd</span></span>                 | <span data-ttu-id="37a30-125">Число, десятичное</span><span class="sxs-lookup"><span data-stu-id="37a30-125">Number, Decimal</span></span>               |
| <span data-ttu-id="37a30-126">Nl</span><span class="sxs-lookup"><span data-stu-id="37a30-126">Nl</span></span>                 | <span data-ttu-id="37a30-127">Число: буква</span><span class="sxs-lookup"><span data-stu-id="37a30-127">Number, Letter</span></span>                |
 
 <span data-ttu-id="37a30-128">XAML определяет вторую грамматику, Доттедксамлнаме, которая используется для уточненных ссылок на свойства и события, а также для присоединенных членов.</span><span class="sxs-lookup"><span data-stu-id="37a30-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="37a30-129">Дополнительные сведения см. в <xref:System.Windows.DependencyProperty> разделе [Общие сведения о языке XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="37a30-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="37a30-130">Строковые значения типа Доттедксамлнаме должны соответствовать следующей грамматике:</span><span class="sxs-lookup"><span data-stu-id="37a30-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="37a30-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="37a30-131">Remarks</span></span>  
 <span data-ttu-id="37a30-132">Полную спецификацию см. в разделе [ \[MS-\]XAML](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="37a30-132">For the complete specification, see [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
