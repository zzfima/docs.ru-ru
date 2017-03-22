---
title: "Оператор RemoveHandler | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
dev_langs:
- VB
helpviewer_keywords:
- RemoveHandler keyword
- RemoveHandler statement
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
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
ms.openlocfilehash: d35de576bd9e267800acc2a9bfd5761dd977622f
ms.lasthandoff: 03/13/2017

---
# <a name="removehandler-statement"></a>Оператор RemoveHandler
Удаляет связь между событием и обработчиком событий.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`event`|Имя обрабатываемого события.|  
|`eventhandler`|Имя процедуры, которая обрабатывает событие.|  
  
## <a name="remarks"></a>Примечания  
 `AddHandler` И `RemoveHandler` инструкции позволяют запускать и останавливать обработку события для конкретного события в любой момент во время выполнения программы.  
  
> [!NOTE]
>  Для пользовательских событий `RemoveHandler` инструкция вызывает событие `RemoveHandler` доступа. Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrEvents&17;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [Обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)   
 [События](../../../visual-basic/programming-guide/language-features/events/index.md)
