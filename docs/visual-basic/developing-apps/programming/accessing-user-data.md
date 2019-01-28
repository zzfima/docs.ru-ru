---
title: Доступ к пользователя (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- domain names [Visual Basic], retrieving
- data [Visual Basic], accessing user data
- My.User object [Visual Basic], tasks
- user data [Visual Basic], domain
- user names [Visual Basic], retrieving
- user data [Visual Basic], accessing
- login names [Visual Basic]
- examples [Visual Basic], accessing user data
ms.assetid: 32492a15-ee59-4a63-a1f1-9b24cc13140a
ms.openlocfilehash: 5ff071aadb189cec839b9cb41d510764a9187363
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605493"
---
# <a name="accessing-user-data-visual-basic"></a>Доступ к пользователя (Visual Basic)
В этом разделе рассматриваются вопросы, связанные с объектом `My.User` и задачами, которые можно выполнять с его помощью.  
  
 Объект `My.User` предоставляет доступ к сведениям о вошедшем в систему пользователе, возвращая объект, реализующий интерфейс <xref:System.Security.Principal.IPrincipal>.  
  
## <a name="tasks"></a>Задачи  
  
|Кому|См.|  
|--------|---------|  
|Получение имени входа пользователя|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|Получение имени домена пользователя, если приложение использует проверку подлинности Windows|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|Определение роли пользователя|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
