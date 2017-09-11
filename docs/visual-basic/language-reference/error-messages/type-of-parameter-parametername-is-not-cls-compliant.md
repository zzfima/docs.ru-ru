---
title: "Тип параметра &quot;&lt;parametername&gt;&quot; не является CLS-совместимым | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40028
- bc40028
dev_langs:
- VB
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 25392d9855b44d9f82157601648384955951475e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="type-of-parameter-39ltparameternamegt39-is-not-cls-compliant"></a><span data-ttu-id="0cb1b-102">Тип параметра "&lt;parametername&gt;" не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="0cb1b-102">Type of parameter &#39;&lt;parametername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="0cb1b-103">Процедура помечена как `<CLSCompliant(True)>` , но объявляет параметр с типом, который помечен как `<CLSCompliant(False)>`, не помечен или не квалифицирован, так как он является несовместимым типом.</span><span class="sxs-lookup"><span data-stu-id="0cb1b-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="0cb1b-104">Для соответствия требованиям, описанным в статье [Независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), процедура должна использовать только типы, соответствующие CLS.</span><span class="sxs-lookup"><span data-stu-id="0cb1b-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="0cb1b-105">Это касается типов параметров, типа возвращаемого значения и типов всех локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="0cb1b-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="0cb1b-106">Следующие типы данных [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не соответствуют CLS:</span><span class="sxs-lookup"><span data-stu-id="0cb1b-106">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="0cb1b-107">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="0cb1b-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="0cb1b-108">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="0cb1b-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="0cb1b-109">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="0cb1b-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="0cb1b-110">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="0cb1b-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="0cb1b-111">При применении <xref:System.CLSCompliantAttribute>к программному элементу, задайте атрибут `isCompliant` параметр либо `True` или `False` , чтобы указать соответствие или несоответствие.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="0cb1b-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="0cb1b-112">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="0cb1b-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="0cb1b-113">Если не применить <xref:System.CLSCompliantAttribute>на элемент, он считается как несоответствующий.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="0cb1b-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="0cb1b-114">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="0cb1b-114">By default, this message is a warning.</span></span> <span data-ttu-id="0cb1b-115">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="0cb1b-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="0cb1b-116">**Идентификатор ошибки:** BC40028</span><span class="sxs-lookup"><span data-stu-id="0cb1b-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0cb1b-117">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0cb1b-117">To correct this error</span></span>  
  
-   <span data-ttu-id="0cb1b-118">Если процедура должна принимать параметр этого конкретного типа, удалите <xref:System.CLSCompliantAttribute>.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="0cb1b-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="0cb1b-119">Процедура не может соответствовать CLS.</span><span class="sxs-lookup"><span data-stu-id="0cb1b-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="0cb1b-120">Если процедура должна быть CLS-совместимыми, измените тип этого параметра на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="0cb1b-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="0cb1b-121">Например, вместо `UInteger` вы можете использовать `Integer`, если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="0cb1b-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="0cb1b-122">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="0cb1b-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="0cb1b-123">При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cb1b-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="0cb1b-124">Например, данные типа `int` часто являются 16-битными в других средах.</span><span class="sxs-lookup"><span data-stu-id="0cb1b-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="0cb1b-125">Если вы принимаете 16-битное целое число из таких компонентов, объявите его как `Short` (а не `Integer`) в управляемом коде [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cb1b-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cb1b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0cb1b-126">See Also</span></span>  
 [<span data-ttu-id="0cb1b-127">\<PAVE НАД настроек написание CLS-совместимого кода</span><span class="sxs-lookup"><span data-stu-id="0cb1b-127">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
