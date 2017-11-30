---
title: "&#39; AddressOf &#39; операнд должен быть именем метода (без скобок)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords: BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02c996f1c94250526982e35395288b07db619db7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a>&#39; AddressOf &#39; операнд должен быть именем метода (без скобок)
Оператор `AddressOf` создает экземпляр делегата процедуры, ссылающийся на конкретную процедуру. Синтаксис выглядит следующим образом.  
  
 `AddressOf` `procedurename`  
  
 Вставить круглые скобки вокруг аргумента `AddressOf`, которые не нужны.  
  
 **Идентификатор ошибки:** BC30577  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Удалите круглые скобки вокруг аргумента `AddressOf`.  
  
2.  Убедитесь, что аргумент является именем метода.  
  
## <a name="see-also"></a>См. также  
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)
