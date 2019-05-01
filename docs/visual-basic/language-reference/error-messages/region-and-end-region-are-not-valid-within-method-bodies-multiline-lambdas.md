---
title: Операторы «#Region» и «#End Region» недопустимы в телах / многострочной лямбды метод
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: c41b95da7e3565ae7aaf332fe49361336e79f7c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013768"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах
`#Region` Блок должен быть объявлен на уровне класса, модуля или пространства имен. Сворачиваемую область может включать один или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.  
  
 **Идентификатор ошибки:** BC32025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что предыдущая процедура завершается должным образом с `End Function` или `End Sub` инструкции.  
  
2. Убедитесь, что `#Region` и `#End Region` директивы находятся в одном блоке кода.  
  
## <a name="see-also"></a>См. также

- [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)
