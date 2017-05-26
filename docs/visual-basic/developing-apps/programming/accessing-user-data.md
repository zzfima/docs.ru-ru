---
title: "Доступ к пользователям (Visual Basic) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- domain names, retrieving
- data [Visual Basic], accessing user data
- My.User object, tasks
- user data, domain
- user names, retrieving
- user data, accessing
- login names
- examples [Visual Basic], accessing user data
ms.assetid: 32492a15-ee59-4a63-a1f1-9b24cc13140a
caps.latest.revision: 17
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ef4607074e1e89bcafdd4262a25070693948f8ff
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="accessing-user-data-visual-basic"></a>Доступ к пользователя (Visual Basic)
В этом разделе рассматриваются вопросы, связанные с объектом `My.User` и задачами, которые можно выполнять с его помощью.  
  
 Объект `My.User` предоставляет доступ к сведениям о вошедшем в систему пользователе, возвращая объект, реализующий интерфейс <xref:System.Security.Principal.IPrincipal>.  
  
## <a name="tasks"></a>Задачи  
  
|Целевой тип|См.|  
|--------|---------|  
|Получение имени входа пользователя|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|Получение имени домена пользователя, если приложение использует проверку подлинности Windows|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|Определение роли пользователя|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>
