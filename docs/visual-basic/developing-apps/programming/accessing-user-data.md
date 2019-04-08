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
ms.openlocfilehash: e5d18adcb331162a72da0adb4018d1d59ecc072e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825304"
---
# <a name="accessing-user-data-visual-basic"></a><span data-ttu-id="66bde-102">Доступ к пользователя (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66bde-102">Accessing User Data (Visual Basic)</span></span>
<span data-ttu-id="66bde-103">В этом разделе рассматриваются вопросы, связанные с объектом `My.User` и задачами, которые можно выполнять с его помощью.</span><span class="sxs-lookup"><span data-stu-id="66bde-103">This section contains topics dealing with the `My.User` object and tasks that you can accomplish with it.</span></span>  
  
 <span data-ttu-id="66bde-104">Объект `My.User` предоставляет доступ к сведениям о вошедшем в систему пользователе, возвращая объект, реализующий интерфейс <xref:System.Security.Principal.IPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="66bde-104">The `My.User` object provides access to information about the logged-on user by returning an object that implements the <xref:System.Security.Principal.IPrincipal> interface.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="66bde-105">Задачи</span><span class="sxs-lookup"><span data-stu-id="66bde-105">Tasks</span></span>  
  
|<span data-ttu-id="66bde-106">Кому</span><span class="sxs-lookup"><span data-stu-id="66bde-106">To</span></span>|<span data-ttu-id="66bde-107">См.</span><span class="sxs-lookup"><span data-stu-id="66bde-107">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="66bde-108">Получение имени входа пользователя</span><span class="sxs-lookup"><span data-stu-id="66bde-108">Get the user's login name</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|<span data-ttu-id="66bde-109">Получение имени домена пользователя, если приложение использует проверку подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="66bde-109">Get the user's domain name, if the application uses Windows authentication</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|<span data-ttu-id="66bde-110">Определение роли пользователя</span><span class="sxs-lookup"><span data-stu-id="66bde-110">Determine the user's role</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="66bde-111">См. также</span><span class="sxs-lookup"><span data-stu-id="66bde-111">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.User>
