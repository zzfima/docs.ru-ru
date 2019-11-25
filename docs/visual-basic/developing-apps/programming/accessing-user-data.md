---
title: Доступ к данным пользователя
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
ms.openlocfilehash: 463d3bc77237482d4cd568b9558bb72cd19e7216
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349214"
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
