---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ffca9a587bdb32afc252f9719eb35e3139dd3f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="ff101-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="ff101-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>
<span data-ttu-id="ff101-103">Подтверждение безопасности с потенциальным соседним узлом завершилось неуспешно.</span><span class="sxs-lookup"><span data-stu-id="ff101-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ff101-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="ff101-104">Description</span></span>  
 <span data-ttu-id="ff101-105">Эта трассировка возникает при попытке установить безопасное соединение с соседним узлом.</span><span class="sxs-lookup"><span data-stu-id="ff101-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="ff101-106">Это может произойти из-за недостаточных или неправильных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="ff101-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="ff101-107">PeerChannel распознает один тип маркеров для строгой идентификации (сертификаты X.509), что обеспечивает строгую модель удостоверения, зависящую от типа проверки подлинности и авторизации, который может быть реализован.</span><span class="sxs-lookup"><span data-stu-id="ff101-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="ff101-108">PeerChannel также обеспечивает поддержку простых приложений посредством использования паролей.</span><span class="sxs-lookup"><span data-stu-id="ff101-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="ff101-109">Пароли могут использоваться только для разрешения входа в сеанс; их нельзя использовать для проверки подлинности сообщений.</span><span class="sxs-lookup"><span data-stu-id="ff101-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="ff101-110">Это связано с тем, что симметричный маркер, общий для участников одноранговой группы, сложно (и не следует) использовать для проверки подлинности источника.</span><span class="sxs-lookup"><span data-stu-id="ff101-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ff101-111">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ff101-111">Troubleshooting</span></span>  
 <span data-ttu-id="ff101-112">Обеспечьте, чтобы все соседние узлы имели соответствующие учетные данные безопасности.</span><span class="sxs-lookup"><span data-stu-id="ff101-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff101-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ff101-113">See Also</span></span>  
 [<span data-ttu-id="ff101-114">Безопасность одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="ff101-114">Peer Channel Security</span></span>](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)  
 [<span data-ttu-id="ff101-115">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ff101-115">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="ff101-116">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ff101-116">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="ff101-117">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="ff101-117">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
