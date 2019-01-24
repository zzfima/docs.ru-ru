---
title: '&#39;#Region&#39; и &#39;#End Region&#39; операторы внутри метода тел / многострочной лямбды недопустимы'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 55399cd123ce4d67cc833f2eabe3230acdafc0bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737219"
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>&#39;#Region&#39; и &#39;#End Region&#39; недопустимы в телах/многострочных лямбда-метод
`#Region` Блок должен быть объявлен на уровне класса, модуля или пространства имен. Сворачиваемую область может включать один или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.  
  
 **Идентификатор ошибки:** BC32025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что предыдущая процедура завершается должным образом с `End Function` или `End Sub` инструкции.  
  
2.  Убедитесь, что `#Region` и `#End Region` директивы находятся в одном блоке кода.  
  
## <a name="see-also"></a>См. также
- [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)
