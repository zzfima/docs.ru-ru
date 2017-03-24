---
title: "Тип члена &quot;&lt;membername&gt;&quot; не является CLS-совместимым | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40025
- vbc40025
dev_langs:
- VB
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3ea35f54cf8f0fb5a11148b8017456feb8d3524a
ms.lasthandoff: 03/13/2017

---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a>Тип члена "&lt;membername&gt;" не является CLS-совместимым
Тип данных, указанный для этого элемента не является частью [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS). Это не ошибка в компоненте, поскольку [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] и [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] поддерживает этот тип данных. Однако другой компонент, написанный в строго CLS-совместимом коде могут не поддерживать этот тип данных. Такой компонент может оказаться невозможным успешно взаимодействовать с данным компонентом.  
  
 Следующие типы данных [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не соответствуют CLS:  
  
-   [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если компонент взаимодействует только с другими [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] компонентов, или не взаимодействует с другие компоненты, не нужно ничего менять.  
  
-   При взаимодействии с компонентом, не записанном для [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], можно определить, либо через отражение, или из документации, является ли он поддерживает этот тип данных. В этом случае не требуется ничего менять.  
  
-   При взаимодействии с компонентом, который не поддерживает этот тип данных, его необходимо заменить на ближайший CLS-совместимый тип. Например, вместо `UInteger` вы можете использовать `Integer`, если вам не нужен диапазон значений, превышающий 2 147 483 647. Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.  
  
-   При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Например, данные типа `uint` часто являются 16-битными в других средах. При передаче 16-разрядного аргумента такому компоненту, следует объявить ее как `UShort` вместо `UInteger` в управляемом [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] кода.  
  
## <a name="see-also"></a>См. также  
 [Отражение](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)   
 [\<PAVE НАД настроек написание CLS-совместимого кода](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
