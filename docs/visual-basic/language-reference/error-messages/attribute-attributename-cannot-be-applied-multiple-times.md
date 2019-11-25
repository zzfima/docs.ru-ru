---
title: Атрибут <attributename> не может применяться многократно
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: f2f4dc428a247275f9919c4a8b6e6944a558eef0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968229"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>Атрибут "\<AttributeName >" не может применяться несколько раз

Атрибут можно применить только один раз. Атрибут `AttributeUsage` определяет, может ли атрибут быть применен более одного раза.  
  
 **Идентификатор ошибки:** BC30663  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что атрибут применяется только один раз.  
  
2. При использовании настраиваемых атрибутов, которые вы разработали, рассмотрите возможность изменения атрибута `AttributeUsage`, чтобы разрешить использование нескольких атрибутов, как показано в следующем примере.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.AttributeUsageAttribute>
- [Создание настраиваемых атрибутов](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
