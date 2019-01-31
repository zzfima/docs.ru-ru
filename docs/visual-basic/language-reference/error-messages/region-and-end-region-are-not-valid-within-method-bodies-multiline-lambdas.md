---
title: Операторы «#Region» и «#End Region» недопустимы в телах / многострочной лямбды метод
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 2a2f5692518c6784dfc6e3be6302f1e8dcf2aaa7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265575"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах
`#Region` Блок должен быть объявлен на уровне класса, модуля или пространства имен. Сворачиваемую область может включать один или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.  
  
 **Идентификатор ошибки:** BC32025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что предыдущая процедура завершается должным образом с `End Function` или `End Sub` инструкции.  
  
2.  Убедитесь, что `#Region` и `#End Region` директивы находятся в одном блоке кода.  
  
## <a name="see-also"></a>См. также
- [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)
