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
# <a name="accessing-user-data-visual-basic"></a><span data-ttu-id="5bcae-102">Доступ к пользователя (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5bcae-102">Accessing User Data (Visual Basic)</span></span>

<span data-ttu-id="5bcae-103">В этом разделе рассматриваются вопросы, связанные с объектом `My.User` и задачами, которые можно выполнять с его помощью.</span><span class="sxs-lookup"><span data-stu-id="5bcae-103">This section contains topics dealing with the `My.User` object and tasks that you can accomplish with it.</span></span>  
  
 <span data-ttu-id="5bcae-104">Объект `My.User` предоставляет доступ к сведениям о вошедшем в систему пользователе, возвращая объект, реализующий интерфейс <xref:System.Security.Principal.IPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="5bcae-104">The `My.User` object provides access to information about the logged-on user by returning an object that implements the <xref:System.Security.Principal.IPrincipal> interface.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="5bcae-105">Задачи</span><span class="sxs-lookup"><span data-stu-id="5bcae-105">Tasks</span></span>  
  
|<span data-ttu-id="5bcae-106">Кому</span><span class="sxs-lookup"><span data-stu-id="5bcae-106">To</span></span>|<span data-ttu-id="5bcae-107">См.</span><span class="sxs-lookup"><span data-stu-id="5bcae-107">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="5bcae-108">Получение имени входа пользователя</span><span class="sxs-lookup"><span data-stu-id="5bcae-108">Get the user's login name</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|<span data-ttu-id="5bcae-109">Получение имени домена пользователя, если приложение использует проверку подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="5bcae-109">Get the user's domain name, if the application uses Windows authentication</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|<span data-ttu-id="5bcae-110">Определение роли пользователя</span><span class="sxs-lookup"><span data-stu-id="5bcae-110">Determine the user's role</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="5bcae-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5bcae-111">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.User>
