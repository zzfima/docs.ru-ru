---
title: "Начальные &#39;. &#39; или &#39;! &#39; может использоваться только внутри &#39; С &#39; инструкции"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords: BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 961f2d737123ab68b200d5fc7658cb81291a5de6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>Начальные &#39;. &#39; или &#39;! &#39; может использоваться только внутри &#39; С &#39; инструкции
Точка (.) или восклицательный знак (!), не находится внутри `With` блок происходит без выражения слева. Доступ к членам (`.`) и доступ к членам словаря (`!`) требуется выражение, задающее элемент, содержащий элемент. Это должно быть расположено слева от метода доступа или в качестве целевого объекта `With` блок, содержащий доступ к члену.  
  
 **Идентификатор ошибки:** BC30157  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что `With` блок имеет правильный формат.  
  
2.  При наличии не `With` блока, добавьте выражение слева от метода доступа, результатом вычисления элемента, содержащего элемент.  
  
## <a name="see-also"></a>См. также  
 [Специальные символы в коде](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
