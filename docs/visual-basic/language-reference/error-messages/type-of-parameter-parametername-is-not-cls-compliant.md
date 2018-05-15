---
title: Тип параметра &#39; &lt;имя_параметра&gt; &#39; не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: 13a4e35cd27ed5aa135cec77c4415f223cba70f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="type-of-parameter-39ltparameternamegt39-is-not-cls-compliant"></a><span data-ttu-id="3b135-102">Тип параметра &#39; &lt;имя_параметра&gt; &#39; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="3b135-102">Type of parameter &#39;&lt;parametername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="3b135-103">Процедура помечена как `<CLSCompliant(True)>` , но объявляет параметр с типом, который помечен как `<CLSCompliant(False)>`, не помечен или не квалифицирован, так как он имеет несоответствующий тип.</span><span class="sxs-lookup"><span data-stu-id="3b135-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="3b135-104">Для соответствия требованиям, описанным в статье [Независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), процедура должна использовать только типы, соответствующие CLS.</span><span class="sxs-lookup"><span data-stu-id="3b135-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="3b135-105">Это касается типов параметров, типа возвращаемого значения и типов всех локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="3b135-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="3b135-106">Следующие типы данных Visual Basic не являются CLS-совместимыми:</span><span class="sxs-lookup"><span data-stu-id="3b135-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="3b135-107">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="3b135-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="3b135-108">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="3b135-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="3b135-109">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="3b135-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="3b135-110">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="3b135-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="3b135-111">При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="3b135-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="3b135-112">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="3b135-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="3b135-113">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="3b135-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="3b135-114">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="3b135-114">By default, this message is a warning.</span></span> <span data-ttu-id="3b135-115">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="3b135-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3b135-116">**Идентификатор ошибки:** BC40028</span><span class="sxs-lookup"><span data-stu-id="3b135-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3b135-117">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="3b135-117">To correct this error</span></span>  
  
-   <span data-ttu-id="3b135-118">Если процедура должна принимать параметр этого конкретного типа, удалите <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3b135-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="3b135-119">Процедура не может соответствовать CLS.</span><span class="sxs-lookup"><span data-stu-id="3b135-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="3b135-120">Если процедура должна быть CLS-совместимыми, измените тип этого параметра на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="3b135-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="3b135-121">Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="3b135-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="3b135-122">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="3b135-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="3b135-123">При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b135-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="3b135-124">Например, данные типа `int` часто являются 16-битными в других средах.</span><span class="sxs-lookup"><span data-stu-id="3b135-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="3b135-125">Если вы принимаете 16-разрядное целое из таких компонентов, объявите его как `Short` вместо `Integer` в управляемом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3b135-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>