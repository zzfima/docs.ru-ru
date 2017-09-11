---
title: "Тип необязательного значения для необязательного параметра &lt;parametername&gt; не является CLS-совместимым | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- BC40042
- vbc40042
dev_langs:
- VB
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
caps.latest.revision: 8
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
ms.openlocfilehash: 4954c241b7cb704ebb9373d837bb1e51c1b44115
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="type-of-optional-value-for-optional-parameter-ltparameternamegt-is-not-cls-compliant"></a><span data-ttu-id="4421f-102">Тип необязательного значения для необязательного параметра &lt;parametername&gt; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="4421f-102">Type of optional value for optional parameter &lt;parametername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="4421f-103">Процедура помечена как `<CLSCompliant(True)>`, но она объявляет [необязательный](../../../visual-basic/language-reference/modifiers/optional.md) параметр со значением по умолчанию несовместимого типа.</span><span class="sxs-lookup"><span data-stu-id="4421f-103">A procedure is marked as `<CLSCompliant(True)>` but declares an [Optional](../../../visual-basic/language-reference/modifiers/optional.md) parameter with default value of a noncompliant type.</span></span>  
  
 <span data-ttu-id="4421f-104">Для соответствия требованиям, описанным в статье [Независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), процедура должна использовать только типы, совместимые с CLS.</span><span class="sxs-lookup"><span data-stu-id="4421f-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="4421f-105">Это касается типов параметров, типа возвращаемого значения и типов всех локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="4421f-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span> <span data-ttu-id="4421f-106">Это также касается значений по умолчанию для необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="4421f-106">It also applies to the default values of optional parameters.</span></span>  
  
 <span data-ttu-id="4421f-107">Следующие типы данных [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не соответствуют CLS:</span><span class="sxs-lookup"><span data-stu-id="4421f-107">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="4421f-108">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="4421f-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="4421f-109">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="4421f-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="4421f-110">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="4421f-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="4421f-111">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="4421f-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="4421f-112">При применении <xref:System.CLSCompliantAttribute>атрибут к программному элементу, задайте атрибут `isCompliant` параметр либо `True` или `False` , чтобы указать соответствие или несоответствие.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="4421f-112">When you apply the <xref:System.CLSCompliantAttribute> attribute to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="4421f-113">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="4421f-113">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="4421f-114">Если не применить <xref:System.CLSCompliantAttribute>на элемент, он считается как несоответствующий.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="4421f-114">If you do not apply <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="4421f-115">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="4421f-115">By default, this message is a warning.</span></span> <span data-ttu-id="4421f-116">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4421f-116">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="4421f-117">**Идентификатор ошибки:** BC40042</span><span class="sxs-lookup"><span data-stu-id="4421f-117">**Error ID:** BC40042</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4421f-118">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4421f-118">To correct this error</span></span>  
  
-   <span data-ttu-id="4421f-119">Если необязательный параметр должен иметь значение по умолчанию этого конкретного типа, удалите <xref:System.CLSCompliantAttribute>.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="4421f-119">If the optional parameter must have a default value of this particular type, remove <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="4421f-120">Процедура не может соответствовать CLS.</span><span class="sxs-lookup"><span data-stu-id="4421f-120">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="4421f-121">Если процедура должна быть совместимой с CLS, измените тип этого значения по умолчанию на ближайший тип, совместимый с CLS.</span><span class="sxs-lookup"><span data-stu-id="4421f-121">If the procedure must be CLS-compliant, change the type of this default value to the closest CLS-compliant type.</span></span> <span data-ttu-id="4421f-122">Например, вместо `UInteger` вы можете использовать `Integer`, если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="4421f-122">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="4421f-123">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="4421f-123">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="4421f-124">При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="4421f-124">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="4421f-125">Например, данные типа `int` часто являются 16-битными в других средах.</span><span class="sxs-lookup"><span data-stu-id="4421f-125">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="4421f-126">Если вы принимаете 16-битное целое число из таких компонентов, объявите его как `Short` (а не `Integer`) в управляемом коде [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="4421f-126">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4421f-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4421f-127">See Also</span></span>  
 [<span data-ttu-id="4421f-128">\<PAVE НАД настроек написание CLS-совместимого кода</span><span class="sxs-lookup"><span data-stu-id="4421f-128">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
