---
title: Атрибут &#39; &lt;attributename&gt; &#39; не может применяться несколько раз
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: df97a4e391406661db98eb1c958c0e12e45b6c49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a>Атрибут &#39; &lt;attributename&gt; &#39; не может применяться несколько раз
Атрибут может применяться только один раз. `AttributeUsage` Атрибут определяет, может ли атрибут применяться более одного раза.  
  
 **Идентификатор ошибки:** BC30663  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что атрибут применяется только один раз.  
  
2.  Если вы используете пользовательские атрибуты, созданные разработчиком, рассмотрите возможность замены их `AttributeUsage` атрибут, чтобы разрешить многократное использование атрибутов, как показано в следующем примере.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.AttributeUsageAttribute>  
 [Создание настраиваемых атрибутов](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
