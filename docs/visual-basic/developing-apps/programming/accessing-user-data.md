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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349214"
---
# <a name="accessing-user-data-visual-basic"></a><span data-ttu-id="a65de-102">Доступ к пользователя (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a65de-102">Accessing User Data (Visual Basic)</span></span>

<span data-ttu-id="a65de-103">В этом разделе рассматриваются вопросы, связанные с объектом `My.User` и задачами, которые можно выполнять с его помощью.</span><span class="sxs-lookup"><span data-stu-id="a65de-103">This section contains topics dealing with the `My.User` object and tasks that you can accomplish with it.</span></span>  
  
 <span data-ttu-id="a65de-104">Объект `My.User` предоставляет доступ к сведениям о вошедшем в систему пользователе, возвращая объект, реализующий интерфейс <xref:System.Security.Principal.IPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="a65de-104">The `My.User` object provides access to information about the logged-on user by returning an object that implements the <xref:System.Security.Principal.IPrincipal> interface.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="a65de-105">Задания</span><span class="sxs-lookup"><span data-stu-id="a65de-105">Tasks</span></span>  
  
|<span data-ttu-id="a65de-106">Чтобы</span><span class="sxs-lookup"><span data-stu-id="a65de-106">To</span></span>|<span data-ttu-id="a65de-107">См.</span><span class="sxs-lookup"><span data-stu-id="a65de-107">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="a65de-108">Получение имени входа пользователя</span><span class="sxs-lookup"><span data-stu-id="a65de-108">Get the user's login name</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|<span data-ttu-id="a65de-109">Получение имени домена пользователя, если приложение использует проверку подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="a65de-109">Get the user's domain name, if the application uses Windows authentication</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|<span data-ttu-id="a65de-110">Определение роли пользователя</span><span class="sxs-lookup"><span data-stu-id="a65de-110">Determine the user's role</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="a65de-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a65de-111">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.User>
