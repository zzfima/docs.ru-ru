---
title: "Доступ к пользователя (Visual Basic)"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 396ae45d26551c3a44a8a8fa6334a744508734a7
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="accessing-user-data-visual-basic"></a><span data-ttu-id="90edf-102">Доступ к пользователя (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90edf-102">Accessing User Data (Visual Basic)</span></span>
<span data-ttu-id="90edf-103">В этом разделе рассматриваются вопросы, связанные с объектом `My.User` и задачами, которые можно выполнять с его помощью.</span><span class="sxs-lookup"><span data-stu-id="90edf-103">This section contains topics dealing with the `My.User` object and tasks that you can accomplish with it.</span></span>  
  
 <span data-ttu-id="90edf-104">Объект `My.User` предоставляет доступ к сведениям о вошедшем в систему пользователе, возвращая объект, реализующий интерфейс <xref:System.Security.Principal.IPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="90edf-104">The `My.User` object provides access to information about the logged-on user by returning an object that implements the <xref:System.Security.Principal.IPrincipal> interface.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="90edf-105">Задачи</span><span class="sxs-lookup"><span data-stu-id="90edf-105">Tasks</span></span>  
  
|<span data-ttu-id="90edf-106">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="90edf-106">To</span></span>|<span data-ttu-id="90edf-107">См.</span><span class="sxs-lookup"><span data-stu-id="90edf-107">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="90edf-108">Получение имени входа пользователя</span><span class="sxs-lookup"><span data-stu-id="90edf-108">Get the user's login name</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|<span data-ttu-id="90edf-109">Получение имени домена пользователя, если приложение использует проверку подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="90edf-109">Get the user's domain name, if the application uses Windows authentication</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|<span data-ttu-id="90edf-110">Определение роли пользователя</span><span class="sxs-lookup"><span data-stu-id="90edf-110">Determine the user's role</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="90edf-111">См. также</span><span class="sxs-lookup"><span data-stu-id="90edf-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>

