---
title: Атрибут <attributename> не может применяться многократно
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 62e84d174e4e218472eda9b7c08ed677e0140438
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278711"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="6987a-102">Атрибут "\<имя_атрибута >" не может использоваться несколько раз</span><span class="sxs-lookup"><span data-stu-id="6987a-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>
<span data-ttu-id="6987a-103">Атрибут может применяться только один раз.</span><span class="sxs-lookup"><span data-stu-id="6987a-103">The attribute can only be applied once.</span></span> <span data-ttu-id="6987a-104">`AttributeUsage` Атрибут определяет, может ли атрибут применен более одного раза.</span><span class="sxs-lookup"><span data-stu-id="6987a-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="6987a-105">**Идентификатор ошибки:** BC30663</span><span class="sxs-lookup"><span data-stu-id="6987a-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6987a-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6987a-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="6987a-107">Убедитесь, что атрибут применяется только один раз.</span><span class="sxs-lookup"><span data-stu-id="6987a-107">Make sure the attribute is only applied once.</span></span>  
  
2.  <span data-ttu-id="6987a-108">Если вы используете настраиваемые атрибуты, которые вы разработали, рекомендуется изменить их `AttributeUsage` атрибут, чтобы разрешить использование нескольких атрибутов, как и в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6987a-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6987a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="6987a-109">See also</span></span>
- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="6987a-110">Создание настраиваемых атрибутов</span><span class="sxs-lookup"><span data-stu-id="6987a-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="6987a-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="6987a-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
