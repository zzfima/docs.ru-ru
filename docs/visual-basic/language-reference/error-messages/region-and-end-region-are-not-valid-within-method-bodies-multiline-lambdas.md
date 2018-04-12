---
title: '&#39; #Region &#39; и &#39; #End Region &#39; операторы внутри метода тел многострочного лямбда-выражения недопустимы'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 614d0c7324bfbf07bc5736c799e8b54937ead081
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>&#39; #Region &#39; и &#39; #End Region &#39; операторы внутри метода тел/многострочных лямбда-выражения недопустимы
`#Region` Блок должен быть объявлен на уровне класса, модуля или пространства имен. Сворачиваемой области может включать один или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.  
  
 **Идентификатор ошибки:** BC32025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что и предыдущая процедура завершается должным образом с `End Function` или `End Sub` инструкции.  
  
2.  Убедитесь, что `#Region` и `#End Region` директивы находятся в одном блоке кода.  
  
## <a name="see-also"></a>См. также  
 [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)
