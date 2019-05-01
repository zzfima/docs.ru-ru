---
title: Тип возвращаемого значения функции <procedurename> несовместим с CLS
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: 5e746981d10ba8e662aebf86f67f08856ba37199
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013750"
---
# <a name="return-type-of-function-procedurename-is-not-cls-compliant"></a><span data-ttu-id="ca5b6-102">Тип возвращаемого значения функции "\<имя_процедуры >" не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="ca5b6-102">Return type of function '\<procedurename>' is not CLS-compliant</span></span>
<span data-ttu-id="ca5b6-103">Объект `Function` процедура помечена как `<CLSCompliant(True)>` , но возвращает тип, который помечен как `<CLSCompliant(False)>`, не помечен или не определен, так как он является несовместимым типом.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="ca5b6-104">Для соответствия требованиям, описанным в статье [Независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), процедура должна использовать только типы, соответствующие CLS.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="ca5b6-105">Это касается типов параметров, типа возвращаемого значения и типов всех локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="ca5b6-106">Следующие типы данных Visual Basic не являются CLS-совместимыми:</span><span class="sxs-lookup"><span data-stu-id="ca5b6-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="ca5b6-107">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="ca5b6-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="ca5b6-108">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="ca5b6-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="ca5b6-109">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="ca5b6-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="ca5b6-110">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="ca5b6-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="ca5b6-111">При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="ca5b6-112">Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="ca5b6-113">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="ca5b6-114">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-114">By default, this message is a warning.</span></span> <span data-ttu-id="ca5b6-115">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ca5b6-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ca5b6-116">**Идентификатор ошибки:** BC40027</span><span class="sxs-lookup"><span data-stu-id="ca5b6-116">**Error ID:** BC40027</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ca5b6-117">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ca5b6-117">To correct this error</span></span>  
  
- <span data-ttu-id="ca5b6-118">Если `Function` процедура должна возвращать этот конкретный тип, удалите <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="ca5b6-119">Процедура не может соответствовать CLS.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-119">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="ca5b6-120">Если `Function` процедуры должны быть CLS-совместимыми, измените тип возвращаемого значения на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="ca5b6-121">Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="ca5b6-122">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="ca5b6-123">При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca5b6-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="ca5b6-124">Например, данные типа `int` часто являются 16-битными в других средах.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="ca5b6-125">Если вы возвращаете 16-разрядное целое число для таких компонентов, объявите его как `Short` вместо `Integer` в управляемом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ca5b6-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>