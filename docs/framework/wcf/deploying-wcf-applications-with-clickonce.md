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
# <a name="deploying-wcf-applications-with-clickonce"></a>Развертывание приложений WCF с помощью ClickOnce
Клиентские приложения, использующие Windows Communication Foundation (WCF), могут быть развернуты с помощью технологии ClickOnce. Эта технология позволяет им использовать преимущества средств защиты среды выполнения, предоставляемых управлением доступом для кода, если приложения снабжены цифровой подписью с надежным сертификатом. Сертификат, используемый для подписывания приложения ClickOnce, должен располагаться в хранилище надежных издателей, а локальная политика безопасности на клиентском компьютере должна быть настроена таким образом, чтобы предоставлять разрешения полного доверия приложениям, подписанным с использованием сертификата издателя.  
  
 Сведения о настройке приложений ClickOnce и доверенных издателей см. в разделе [Настройка доверенных издателей ClickOnce](https://docs.microsoft.com/previous-versions/dotnet/articles/ms996418(v=msdn.10)).  
  
## <a name="see-also"></a>См. также:

- [Общие сведения о развертывании доверенных приложений](/visualstudio/deployment/trusted-application-deployment-overview)
- [Развертывание ClickOnce для приложений Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/wh45kb66(v=vs.90))
