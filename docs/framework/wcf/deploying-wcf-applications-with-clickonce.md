---
title: "Развертывание приложений WCF с помощью ClickOnce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 714e8341c58e5337d8e45bf61b48137d33fa51b9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="bc7c2-102">Развертывание приложений WCF с помощью ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bc7c2-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="bc7c2-103">Клиентские приложения, использующие [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], могут развертываться с использованием технологии ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="bc7c2-103">Client applications using [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="bc7c2-104">Эта технология позволяет им использовать преимущества средств защиты среды выполнения, предоставляемых управлением доступом для кода, если приложения снабжены цифровой подписью с надежным сертификатом.</span><span class="sxs-lookup"><span data-stu-id="bc7c2-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="bc7c2-105">Сертификат, используемый для подписывания приложения ClickOnce, должен располагаться в хранилище надежных издателей, а локальная политика безопасности на клиентском компьютере должна быть настроена таким образом, чтобы предоставлять разрешения полного доверия приложениям, подписанным с использованием сертификата издателя.</span><span class="sxs-lookup"><span data-stu-id="bc7c2-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="bc7c2-106">Сведения о настройке приложения ClickOnce и доверенных издателей см. в разделе [Настройка надежных издателей ClickOnce](http://go.microsoft.com/fwlink/?LinkId=94774).</span><span class="sxs-lookup"><span data-stu-id="bc7c2-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](http://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc7c2-107">См. также</span><span class="sxs-lookup"><span data-stu-id="bc7c2-107">See Also</span></span>  
 [<span data-ttu-id="bc7c2-108">Общие сведения о развертывании доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="bc7c2-108">Trusted Application Deployment Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [<span data-ttu-id="bc7c2-109">Развертывание ClickOnce для Windows Forms приложений</span><span class="sxs-lookup"><span data-stu-id="bc7c2-109">ClickOnce Deployment for Windows Forms Applications</span></span>](http://go.microsoft.com/fwlink/?LinkId=94776)
