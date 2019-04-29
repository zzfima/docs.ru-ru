---
title: Атрибут <attributename> не может применяться многократно
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: da4a766e2617308cb33b9673a88db9e7a954152a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935321"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>Атрибут "\<имя_атрибута >" не может использоваться несколько раз
Атрибут может применяться только один раз. `AttributeUsage` Атрибут определяет, может ли атрибут применен более одного раза.  
  
 **Идентификатор ошибки:** BC30663  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что атрибут применяется только один раз.  
  
2. Если вы используете настраиваемые атрибуты, которые вы разработали, рекомендуется изменить их `AttributeUsage` атрибут, чтобы разрешить использование нескольких атрибутов, как и в следующем примере.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.AttributeUsageAttribute>
- [Создание настраиваемых атрибутов](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
