---
title: "Другие структуры управления (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 639571b493037f26951bd8fbf140d7bce3244889
ms.lasthandoff: 03/13/2017

---
# <a name="other-control-structures-visual-basic"></a>Другие структуры управления (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет структур элементов управления, которые помогают удаления ресурсов или уменьшения числа повторений ссылок на объект.  
  
## <a name="usingend-using-construction"></a>С помощью... С помощью конструкции End  
 `Using...End Using` Конструкции устанавливает блок операторов, в котором следует использовать ресурсы, например SQL-соединение. При необходимости можно запросить ресурс с `Using` инструкции. После выхода из `Using` блока [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически удаляет ресурс, чтобы он доступен для использования другим кодом. Ресурс должен быть локальным и допускать удаление. Дополнительные сведения см. в разделе [с помощью инструкции](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>С помощью... Завершение создания  
 `With...End With` Позволяет указать ссылку на объект один раз и затем запустить последовательность операторов, доступа к его членам. Это может упростить код и повысить производительность, поскольку [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не восстанавливает ссылку для каждого оператора, который обращается к ней. Дополнительные сведения см. в разделе [с... Заканчивается инструкция](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>См. также  
 [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Структуры критериев](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [С помощью инструкции](../../../../visual-basic/language-reference/statements/using-statement.md)   
 [Оператор With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
