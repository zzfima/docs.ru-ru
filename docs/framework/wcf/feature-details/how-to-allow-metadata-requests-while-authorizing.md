---
title: Практическое руководство. Разрешение запросов метаданных в процессе авторизации
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6b0b331da49fca7be5106610e4b6f144220cc849
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a><span data-ttu-id="5a1d9-102">Практическое руководство. Разрешение запросов метаданных в процессе авторизации</span><span class="sxs-lookup"><span data-stu-id="5a1d9-102">How To: Allow Metadata Requests While Authorizing</span></span>
<span data-ttu-id="5a1d9-103">В процессе настраиваемой авторизации может потребоваться разрешить обработку запроса для метаданных.</span><span class="sxs-lookup"><span data-stu-id="5a1d9-103">During custom authorization, it may be necessary to allow a request for metadata to be processed.</span></span> <span data-ttu-id="5a1d9-104">Следующий раздел содержит пошаговое руководство для проверки такого запроса.</span><span class="sxs-lookup"><span data-stu-id="5a1d9-104">The following topic walks through the steps to validate such a request.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5a1d9-105"> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] авторизация, в разделе [авторизации](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="5a1d9-105"> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] authorization, see [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
### <a name="to-allow-metadata-requests-during-authorization"></a><span data-ttu-id="5a1d9-106">Разрешение запросов метаданных в процессе авторизации</span><span class="sxs-lookup"><span data-stu-id="5a1d9-106">To allow metadata requests during authorization</span></span>  
  
1.  <span data-ttu-id="5a1d9-107">Создайте расширение класса <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="5a1d9-107">Create an extension of the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
2.  <span data-ttu-id="5a1d9-108">Переопределите метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a1d9-108">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="5a1d9-109">Метод возвращает логическое значение `true` или `false`, в зависимости от того, разрешена ли авторизация.</span><span class="sxs-lookup"><span data-stu-id="5a1d9-109">The method returns `true` or `false` depending on whether authorization is allowed.</span></span> <span data-ttu-id="5a1d9-110">Информация о текущей процедуре находится в классе <xref:System.ServiceModel.OperationContext> и передается как параметр методу.</span><span class="sxs-lookup"><span data-stu-id="5a1d9-110">Information about the current procedure is found in the <xref:System.ServiceModel.OperationContext> passed as a parameter to the method.</span></span>  
  
3.  <span data-ttu-id="5a1d9-111">При переопределении проверяются имя контракта, пространство имен и действие, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5a1d9-111">In the override, check the contract name, namespace, and the action as shown in the following example.</span></span> <span data-ttu-id="5a1d9-112">При выполнении этих условий возвращается логическое значение `true.`</span><span class="sxs-lookup"><span data-stu-id="5a1d9-112">If the conditions are valid, then return `true.`</span></span>  
  
4.  <span data-ttu-id="5a1d9-113">Используйте точку расширения для использования класса.</span><span class="sxs-lookup"><span data-stu-id="5a1d9-113">Use the extensibility point to employ the class.</span></span> <span data-ttu-id="5a1d9-114">Дополнительные сведения см. в разделе [как: Создание пользовательского диспетчера авторизации для службы](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="5a1d9-114">For more information, see [How to: Create a Custom Authorization Manager for a Service](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a1d9-115">Пример</span><span class="sxs-lookup"><span data-stu-id="5a1d9-115">Example</span></span>  
 <span data-ttu-id="5a1d9-116">В следующем примере показано переопределение метода <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a1d9-116">The following example shows an override of the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span>  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5a1d9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5a1d9-117">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [<span data-ttu-id="5a1d9-118">Авторизация</span><span class="sxs-lookup"><span data-stu-id="5a1d9-118">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="5a1d9-119">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="5a1d9-119">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
