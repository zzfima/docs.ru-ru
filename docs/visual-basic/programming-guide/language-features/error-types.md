---
title: "Типы ошибок (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors, Visual Basic
- run-time errors, types of errors
- syntax errors, Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d48756b74baf757f043e68124d8b65c2f613e595
ms.lasthandoff: 03/13/2017

---
# <a name="error-types-visual-basic"></a>Типы ошибок (Visual Basic)
В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], ошибки (также называемый *исключения*) делятся на три категории: синтаксические ошибки, ошибки времени выполнения и логических ошибок.  
  
## <a name="syntax-errors"></a>Синтаксические ошибки  
 *Синтаксические ошибки* те, которые появляются при написании кода. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]проверяет код при вводе в **редактор кода** окна и предупредит вас, если вы сделаете ошибку, например, неправильное написание слова или неправильное использование элемента языка. Синтаксические ошибки являются наиболее распространенным типом ошибки. Их легко исправить в среде кодирования по мере их появления.  
  
> [!NOTE]
>  `Option Explicit` Инструкция является одним из средств предотвращения синтаксических ошибок. Принудительно объявлять, заранее, все переменные для использования в приложении. Таким образом когда эти переменные используются в коде, опечатки немедленно обнаруживаются и могут быть исправлены.  
  
## <a name="run-time-errors"></a>Ошибки во время выполнения  
 *Ошибки во время выполнения* те, которые отображаются только после компиляции и выполнения кода. Они включают в себя код, который может отображаться правильно, он не содержат синтаксических ошибок, но не выполняются. Например может правильно написать строку кода для открытия файла. Но если файл поврежден, приложение не может выполнить `Open` функции и будет остановлено. Большинство ошибок времени выполнения можно устранить, переписав ошибочный код и перекомпилировать и запустить приложение.  
  
## <a name="logic-errors"></a>Логические ошибки  
 *Логические ошибки* те, которые выявляются при использования приложения. Они являются большинство часто нежелательных или непредвиденных результатов в ответ на действия пользователя. Например, ошибочное нажатие клавиши или другое внешнее воздействие может вызвать прекращение работы в ожидаемом приложения или вообще. Логические ошибки — обычно наиболее сложно исправить, так как он не всегда ясно их происхождение.  
  
## <a name="see-also"></a>См. также  
 [Оператор Try... Catch... Finally (Visual Basic)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Основы отладки](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)
