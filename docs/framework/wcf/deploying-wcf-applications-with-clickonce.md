---
title: Развертывание приложений WCF с помощью ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: b520931751bbba00d440b46657962ad3f1e41cd3
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802232"
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="2a2f2-102">Развертывание приложений WCF с помощью ClickOnce</span><span class="sxs-lookup"><span data-stu-id="2a2f2-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="2a2f2-103">Клиентские приложения, использующие Windows Communication Foundation (WCF), могут быть развернуты с помощью технологии ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-103">Client applications using Windows Communication Foundation (WCF) may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="2a2f2-104">Эта технология позволяет им использовать преимущества средств защиты среды выполнения, предоставляемых управлением доступом для кода, если приложения снабжены цифровой подписью с надежным сертификатом.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="2a2f2-105">Сертификат, используемый для подписывания приложения ClickOnce, должен располагаться в хранилище надежных издателей, а локальная политика безопасности на клиентском компьютере должна быть настроена таким образом, чтобы предоставлять разрешения полного доверия приложениям, подписанным с использованием сертификата издателя.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="2a2f2-106">Сведения о настройке приложений ClickOnce и доверенных издателей см. в разделе [Настройка доверенных издателей ClickOnce](https://docs.microsoft.com/previous-versions/dotnet/articles/ms996418(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="2a2f2-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](https://docs.microsoft.com/previous-versions/dotnet/articles/ms996418(v=msdn.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a2f2-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a2f2-107">See also</span></span>

- [<span data-ttu-id="2a2f2-108">Общие сведения о развертывании доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="2a2f2-108">Trusted Application Deployment Overview</span></span>](/visualstudio/deployment/trusted-application-deployment-overview)
- <span data-ttu-id="2a2f2-109">[Развертывание ClickOnce для приложений Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/wh45kb66(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2a2f2-109">[ClickOnce Deployment for Windows Forms Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/wh45kb66(v=vs.90))</span></span>
