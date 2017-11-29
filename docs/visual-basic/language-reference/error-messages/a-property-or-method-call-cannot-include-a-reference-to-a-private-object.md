---
title: "Нельзя включить ссылку на закрытый объект при вызове свойства или функции в качестве аргумента или возвращаемого значения"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cce2bc67beb7e4ac0664b5b7240f5eb3ea0204f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a>Нельзя включить ссылку на закрытый объект при вызове свойства или функции в качестве аргумента или возвращаемого значения
Некоторые из возможных причин этой ошибки:  
  
-   клиент вызвал свойство или метод внепроцессного компонента и предпринял попытку передать ссылку на закрытый объект в качестве одного из аргументов;  
  
-   внепроцессный компонент задействовал для клиента метод обратного вызова и предпринял попытку передать ссылку на закрытый объект;  
  
-   внепроцессный компонент предпринял попытку передать ссылку на закрытый объект в качестве аргумента события, которые он вызывал;  
  
-   клиент предпринял попытку назначить ссылку на закрытый объект для аргумента `ByRef` события, которое он обрабатывал.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Удалите ссылку.  
  
## <a name="see-also"></a>См. также  
 [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)
