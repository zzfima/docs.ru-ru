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
# <a name="accessing-user-data-visual-basic"></a><span data-ttu-id="4a683-102">Доступ к пользователя (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a683-102">Accessing User Data (Visual Basic)</span></span>
<span data-ttu-id="4a683-103">В этом разделе рассматриваются вопросы, связанные с объектом `My.User` и задачами, которые можно выполнять с его помощью.</span><span class="sxs-lookup"><span data-stu-id="4a683-103">This section contains topics dealing with the `My.User` object and tasks that you can accomplish with it.</span></span>  
  
 <span data-ttu-id="4a683-104">Объект `My.User` предоставляет доступ к сведениям о вошедшем в систему пользователе, возвращая объект, реализующий интерфейс <xref:System.Security.Principal.IPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="4a683-104">The `My.User` object provides access to information about the logged-on user by returning an object that implements the <xref:System.Security.Principal.IPrincipal> interface.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="4a683-105">Задачи</span><span class="sxs-lookup"><span data-stu-id="4a683-105">Tasks</span></span>  
  
|<span data-ttu-id="4a683-106">Кому</span><span class="sxs-lookup"><span data-stu-id="4a683-106">To</span></span>|<span data-ttu-id="4a683-107">См.</span><span class="sxs-lookup"><span data-stu-id="4a683-107">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="4a683-108">Получение имени входа пользователя</span><span class="sxs-lookup"><span data-stu-id="4a683-108">Get the user's login name</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|<span data-ttu-id="4a683-109">Получение имени домена пользователя, если приложение использует проверку подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="4a683-109">Get the user's domain name, if the application uses Windows authentication</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|<span data-ttu-id="4a683-110">Определение роли пользователя</span><span class="sxs-lookup"><span data-stu-id="4a683-110">Determine the user's role</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="4a683-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4a683-111">See also</span></span>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
