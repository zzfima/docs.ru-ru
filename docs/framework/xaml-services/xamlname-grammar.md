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
# <a name="xamlname-grammar"></a><span data-ttu-id="484b3-102">Грамматика XamlName</span><span class="sxs-lookup"><span data-stu-id="484b3-102">XamlName Grammar</span></span>
<span data-ttu-id="484b3-103">Грамматика Имяxaml — это специальная грамматика, определенная в спецификации языка XAML [MS-XAML], которая создается здесь для удобства.</span><span class="sxs-lookup"><span data-stu-id="484b3-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="484b3-104">Из спецификации XAML</span><span class="sxs-lookup"><span data-stu-id="484b3-104">From the XAML Specification</span></span>  
 <span data-ttu-id="484b3-105">Спецификация [MS-XAML] определяет грамматику Имяxaml для определения набора допустимых символьных идентификаторов, используемых для типов и свойств.</span><span class="sxs-lookup"><span data-stu-id="484b3-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="484b3-106">Строковые значения типа Имяxaml должны соответствовать следующей грамматике:</span><span class="sxs-lookup"><span data-stu-id="484b3-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```xaml  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="484b3-107">Предполагается, что следующие общие значения категории определены в базе данных символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="484b3-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  

| <span data-ttu-id="484b3-108">Категория Юникода</span><span class="sxs-lookup"><span data-stu-id="484b3-108">Unicode category</span></span>   | <span data-ttu-id="484b3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="484b3-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="484b3-110">Lu</span><span class="sxs-lookup"><span data-stu-id="484b3-110">Lu</span></span>                 | <span data-ttu-id="484b3-111">Буква: прописные буквы</span><span class="sxs-lookup"><span data-stu-id="484b3-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="484b3-112">Ll</span><span class="sxs-lookup"><span data-stu-id="484b3-112">Ll</span></span>                 | <span data-ttu-id="484b3-113">Буква: строчные буквы</span><span class="sxs-lookup"><span data-stu-id="484b3-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="484b3-114">Lt</span><span class="sxs-lookup"><span data-stu-id="484b3-114">Lt</span></span>                 | <span data-ttu-id="484b3-115">Буква: заглавный регистр</span><span class="sxs-lookup"><span data-stu-id="484b3-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="484b3-116">Lm</span><span class="sxs-lookup"><span data-stu-id="484b3-116">Lm</span></span>                 | <span data-ttu-id="484b3-117">Буква: модификатор</span><span class="sxs-lookup"><span data-stu-id="484b3-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="484b3-118">Lo</span><span class="sxs-lookup"><span data-stu-id="484b3-118">Lo</span></span>                 | <span data-ttu-id="484b3-119">Буква: другие</span><span class="sxs-lookup"><span data-stu-id="484b3-119">Letter, Other</span></span>                 |
| <span data-ttu-id="484b3-120">Mn</span><span class="sxs-lookup"><span data-stu-id="484b3-120">Mn</span></span>                 | <span data-ttu-id="484b3-121">Пометить, без промежутков</span><span class="sxs-lookup"><span data-stu-id="484b3-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="484b3-122">Mc</span><span class="sxs-lookup"><span data-stu-id="484b3-122">Mc</span></span>                 | <span data-ttu-id="484b3-123">Метка: комбинированная</span><span class="sxs-lookup"><span data-stu-id="484b3-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="484b3-124">Nd</span><span class="sxs-lookup"><span data-stu-id="484b3-124">Nd</span></span>                 | <span data-ttu-id="484b3-125">Число, десятичное</span><span class="sxs-lookup"><span data-stu-id="484b3-125">Number, Decimal</span></span>               |
| <span data-ttu-id="484b3-126">Nl</span><span class="sxs-lookup"><span data-stu-id="484b3-126">Nl</span></span>                 | <span data-ttu-id="484b3-127">Число: буква</span><span class="sxs-lookup"><span data-stu-id="484b3-127">Number, Letter</span></span>                |
 
 <span data-ttu-id="484b3-128">XAML определяет вторую грамматику, Доттедксамлнаме, которая используется для уточненных ссылок на свойства и события, а также для присоединенных членов.</span><span class="sxs-lookup"><span data-stu-id="484b3-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="484b3-129">Дополнительные сведения см. в разделе <xref:System.Windows.DependencyProperty> и [Общие сведения о XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md).</span><span class="sxs-lookup"><span data-stu-id="484b3-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../../desktop-wpf/fundamentals/xaml.md).</span></span>  
  
 <span data-ttu-id="484b3-130">Строковые значения типа Доттедксамлнаме должны соответствовать следующей грамматике:</span><span class="sxs-lookup"><span data-stu-id="484b3-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="484b3-131">Заметки</span><span class="sxs-lookup"><span data-stu-id="484b3-131">Remarks</span></span>  
 <span data-ttu-id="484b3-132">Полную спецификацию см. в разделе [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="484b3-132">For the complete specification, see [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
