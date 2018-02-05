---
title: "Использование обработчиков исключений с пользовательской фильтрацией"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user-filtered exceptions
- exceptions, user-filtered
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1f5eb735262ee7ef69e200b1249c7b1c4a1e2ac2
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="using-user-filtered-exception-handlers"></a>Использование обработчиков исключений с пользовательской фильтрацией
Сейчас Visual Basic поддерживает исключения с пользовательской фильтрацией. Обработчики исключений с пользовательской фильтрацией перехватывают и обрабатывают исключения с учетом определенных для исключения требований. Эти обработчики используют инструкцию **Catch** с ключевым словом **When**.  
  
 Этот метод удобен, когда конкретный объект исключения соответствует нескольким ошибкам. В этом случае у объекта обычно есть свойство, которое содержит код ошибки. С помощью кода ошибки можно выбрать конкретную ошибку, которую вы хотите обработать в инструкции **Catch**.  
  
 В следующем примере Visual Basic демонстрируются инструкции **Catch/When**.  
  
```  
Try  
      'Try statements.  
   Catch When Err = VBErr_ClassLoadException  
      'Catch statements.  
End Try  
```  
  
 Выражение для предложения пользовательской фильтрации не ограничено. При возникновении исключения в выражении с пользовательской фильтрацией это исключение отбрасывается, а выражение фильтрации считается равным false. В этом случае среда CLR продолжает поиск обработчика для текущего исключения.  
  
## <a name="combining-the-specific-exception-and-the-user-filtered-clauses"></a>Объединение конкретного исключения и условий пользовательской фильтрации  
 Оператор catch может содержать как конкретное исключение, так и условия пользовательской фильтрации. Сначала среда выполнения проверяет конкретное исключение. Если проверка пройдена, среда выполнения выполняет фильтр пользователя. Общий фильтр может содержать ссылку на переменную, объявленную в классе фильтра. Обратите внимание, что порядок двух выражений фильтра изменить нельзя.  
  
 В следующем примере Visual Basic демонстрируется конкретное исключение `ClassLoadException` в инструкции **Catch**, а также предложение для пользовательской фильтрации с использованием ключевого слова **When**.  
  
```  
Try  
      'Try statements.  
   Catch cle As ClassLoadException When cle.IsRecoverable()  
      'Catch statements.  
End Try  
```  

## <a name="see-also"></a>См. также
[Исключения](index.md)
