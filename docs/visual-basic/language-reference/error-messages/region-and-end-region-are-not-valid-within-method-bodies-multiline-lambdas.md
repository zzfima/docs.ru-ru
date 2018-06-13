---
title: '&#39;#Region&#39; и &#39;#End Region&#39; недопустимы в метод тел многострочного лямбда-выражения'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: bf3843e0ec3009f3dc7d60e91c340a7f20543231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593237"
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>&#39;#Region&#39; и &#39;#End Region&#39; недопустимы в телах/многострочной лямбде метод
`#Region` Блок должен быть объявлен на уровне класса, модуля или пространства имен. Сворачиваемой области может включать один или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.  
  
 **Идентификатор ошибки:** BC32025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что и предыдущая процедура завершается должным образом с `End Function` или `End Sub` инструкции.  
  
2.  Убедитесь, что `#Region` и `#End Region` директивы находятся в одном блоке кода.  
  
## <a name="see-also"></a>См. также  
 [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)
