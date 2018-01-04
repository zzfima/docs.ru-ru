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
ms.workload: dotnet
ms.openlocfilehash: 0e87e01c39c5f50ff3f4d4e9479a68e19cceb90f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-wcf-applications-with-clickonce"></a>Развертывание приложений WCF с помощью ClickOnce
Клиентские приложения, использующие [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], могут развертываться с использованием технологии ClickOnce. Эта технология позволяет им использовать преимущества средств защиты среды выполнения, предоставляемых управлением доступом для кода, если приложения снабжены цифровой подписью с надежным сертификатом. Сертификат, используемый для подписывания приложения ClickOnce, должен располагаться в хранилище надежных издателей, а локальная политика безопасности на клиентском компьютере должна быть настроена таким образом, чтобы предоставлять разрешения полного доверия приложениям, подписанным с использованием сертификата издателя.  
  
 Сведения о настройке приложения ClickOnce и доверенных издателей см. в разделе [Настройка надежных издателей ClickOnce](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о развертывании доверенных приложений](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [Развертывание ClickOnce для Windows Forms приложений](http://go.microsoft.com/fwlink/?LinkId=94776)
