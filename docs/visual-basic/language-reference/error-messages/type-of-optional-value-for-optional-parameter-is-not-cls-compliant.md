---
title: Тип необязательного значения для необязательного параметра &lt;имя_параметра&gt; не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
ms.openlocfilehash: dd77cd8cbd36f7681e2597d908dd8e55bf249392
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594353"
---
# <a name="type-of-optional-value-for-optional-parameter-ltparameternamegt-is-not-cls-compliant"></a><span data-ttu-id="87e22-102">Тип необязательного значения для необязательного параметра &lt;имя_параметра&gt; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="87e22-102">Type of optional value for optional parameter &lt;parametername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="87e22-103">Процедура помечена как `<CLSCompliant(True)>`, но она объявляет [необязательный](../../../visual-basic/language-reference/modifiers/optional.md) параметр со значением по умолчанию несовместимого типа.</span><span class="sxs-lookup"><span data-stu-id="87e22-103">A procedure is marked as `<CLSCompliant(True)>` but declares an [Optional](../../../visual-basic/language-reference/modifiers/optional.md) parameter with default value of a noncompliant type.</span></span>  
  
 <span data-ttu-id="87e22-104">Для соответствия требованиям, описанным в статье [Независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), процедура должна использовать только типы, совместимые с CLS.</span><span class="sxs-lookup"><span data-stu-id="87e22-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="87e22-105">Это касается типов параметров, типа возвращаемого значения и типов всех локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="87e22-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span> <span data-ttu-id="87e22-106">Это также касается значений по умолчанию для необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="87e22-106">It also applies to the default values of optional parameters.</span></span>  
  
 <span data-ttu-id="87e22-107">Следующие типы данных Visual Basic не являются CLS-совместимыми:</span><span class="sxs-lookup"><span data-stu-id="87e22-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="87e22-108">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="87e22-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="87e22-109">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="87e22-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="87e22-110">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="87e22-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="87e22-111">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="87e22-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="87e22-112">Когда вы применяете атрибут <xref:System.CLSCompliantAttribute> к программному элементу, вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать на соответствие или несоответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="87e22-112">When you apply the <xref:System.CLSCompliantAttribute> attribute to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="87e22-113">Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.</span><span class="sxs-lookup"><span data-stu-id="87e22-113">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="87e22-114">Если вы не примените <xref:System.CLSCompliantAttribute> к элементу, он считается несоответствующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="87e22-114">If you do not apply <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="87e22-115">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="87e22-115">By default, this message is a warning.</span></span> <span data-ttu-id="87e22-116">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="87e22-116">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="87e22-117">**Идентификатор ошибки:** BC40042</span><span class="sxs-lookup"><span data-stu-id="87e22-117">**Error ID:** BC40042</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="87e22-118">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="87e22-118">To correct this error</span></span>  
  
-   <span data-ttu-id="87e22-119">Если необязательный параметр должен иметь значение по умолчанию этого конкретного типа, удалите <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="87e22-119">If the optional parameter must have a default value of this particular type, remove <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="87e22-120">Процедура не может соответствовать CLS.</span><span class="sxs-lookup"><span data-stu-id="87e22-120">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="87e22-121">Если процедура должна быть совместимой с CLS, измените тип этого значения по умолчанию на ближайший тип, совместимый с CLS.</span><span class="sxs-lookup"><span data-stu-id="87e22-121">If the procedure must be CLS-compliant, change the type of this default value to the closest CLS-compliant type.</span></span> <span data-ttu-id="87e22-122">Например, вместо `UInteger` вы можете использовать `Integer`, если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="87e22-122">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="87e22-123">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="87e22-123">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="87e22-124">При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87e22-124">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="87e22-125">Например, данные типа `int` часто являются 16-битными в других средах.</span><span class="sxs-lookup"><span data-stu-id="87e22-125">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="87e22-126">Если вы принимаете 16-разрядное целое из таких компонентов, объявите его как `Short` вместо `Integer` в управляемом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="87e22-126">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>