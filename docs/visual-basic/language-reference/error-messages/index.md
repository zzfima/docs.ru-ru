---
title: "Сообщения об ошибке (Visual Basic) | Документация Майкрософт"
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
- errors [Visual Basic]
- error messages
- trappable errors
- errors [Visual Basic], trappable
ms.assetid: f2dda05b-baef-41f5-8bb1-598bd7cf239f
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e22d81efef735f4b6619054cb15f21790efabf5e
ms.lasthandoff: 03/13/2017

---
# <a name="error-messages-visual-basic"></a>Сообщения об ошибке (Visual Basic)
При записи, компиляции или выполнении приложения Visual Basic возможны ошибки следующих типов.  
  
1.  Ошибки во время разработки, то есть при написании приложения в Visual Studio.  
  
2.  Ошибки компиляции, возникающие при компиляции приложения в Visual Studio или из командной строки.  
  
3.  Ошибки времени выполнения, возникающие при выполнении приложения в Visual Studio или в виде отдельного исполняемого файла.  
  
 Сведения о способах устранения некоторых ошибок можно найти в статье [Additional Resources for Visual Basic Programmers](../../../visual-basic/getting-started/additional-resources.md) (Дополнительные ресурсы для программирования на Visual Basic).  
  
## <a name="run-time-errors"></a>Ошибки времени выполнения  
 Если приложение Visual Basic пытается выполнить действие, которое невозможно в текущей системе, то во время выполнения возникает ошибка, и [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] создает объект `Exception`. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] может создавать с помощью инструкции `Throw` пользовательские ошибки с любым типом данных, включая объекты `Exception`. Приложение может идентифицировать ошибки, отображая номер ошибки и сообщение перехваченного исключения. Если ошибка не будет перехвачена, приложение завершается.  
  
 Код может перехватывать и проверять ошибки времени выполнения. Если вы заключите код, создающий ошибку, в блок `Try`, вы сможете перехватить любую созданную ошибку в соответствующем блоке `Catch`. Сведения о том, как в коде отлавливать ошибки во время выполнения и реагировать на них, можно найти в статье [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Оператор Try...Catch...Finally).  
  
## <a name="compile-time-errors"></a>Ошибки времени компиляции  
 Если компилятор Visual Basic обнаруживает проблему в коде, возникает ошибка времени компиляции. В редакторе кода можно легко определить, какая строка кода вызвала ошибку. Строка с ошибкой подчеркивается волнистой линий. Если навести курсор на подчеркнутый фрагмент, появляется сообщение об ошибке. Также его можно увидеть вместе с другими сообщениями в **списке ошибок**.  
  
 Если идентификатор подчеркивается волнистой линией, а под крайним правым символом есть короткое подчеркивание, это означает возможность создать заглушку для класса, конструктора, метода, свойства, поля или перечисления. Дополнительные сведения см. в статье [Generate From Usage](https://docs.microsoft.com/cpp/misc/generate-from-usage) (Создание из использования).  
  
 Если вы будете правильно учитывать предупреждения компилятора Visual Basic, ваш код будет работать быстрее и с меньшим количеством ошибок. Эти предупреждения сообщают о том, что в коде могут возникнуть ошибки при запуске приложения. Например, компилятор предупреждает о вызове члена неопределенной объектной переменной, о возврате из функции без задания возвращаемого значения, а также о выполнении блока `Try` с ошибками в логике перехвата исключений. Дополнительные сведения о предупреждениях, в том числе о возможности включать и отключать их, см. в статье [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic) (Настройка предупреждений в Visual Basic).
