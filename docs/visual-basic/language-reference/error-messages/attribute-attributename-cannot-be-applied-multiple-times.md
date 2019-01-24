---
title: Атрибут &#39; &lt;attributename&gt; &#39; не может использоваться несколько раз
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 6609ce299799bc3c4b78d48478e99e4d4101dd72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565167"
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a><span data-ttu-id="7b31b-102">Атрибут &#39; &lt;attributename&gt; &#39; не может использоваться несколько раз</span><span class="sxs-lookup"><span data-stu-id="7b31b-102">Attribute &#39;&lt;attributename&gt;&#39; cannot be applied multiple times</span></span>
<span data-ttu-id="7b31b-103">Атрибут может применяться только один раз.</span><span class="sxs-lookup"><span data-stu-id="7b31b-103">The attribute can only be applied once.</span></span> <span data-ttu-id="7b31b-104">`AttributeUsage` Атрибут определяет, может ли атрибут применен более одного раза.</span><span class="sxs-lookup"><span data-stu-id="7b31b-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="7b31b-105">**Идентификатор ошибки:** BC30663</span><span class="sxs-lookup"><span data-stu-id="7b31b-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7b31b-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7b31b-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="7b31b-107">Убедитесь, что атрибут применяется только один раз.</span><span class="sxs-lookup"><span data-stu-id="7b31b-107">Make sure the attribute is only applied once.</span></span>  
  
2.  <span data-ttu-id="7b31b-108">Если вы используете настраиваемые атрибуты, которые вы разработали, рекомендуется изменить их `AttributeUsage` атрибут, чтобы разрешить использование нескольких атрибутов, как и в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7b31b-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b31b-109">См. также</span><span class="sxs-lookup"><span data-stu-id="7b31b-109">See also</span></span>
- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="7b31b-110">Создание настраиваемых атрибутов</span><span class="sxs-lookup"><span data-stu-id="7b31b-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="7b31b-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="7b31b-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
