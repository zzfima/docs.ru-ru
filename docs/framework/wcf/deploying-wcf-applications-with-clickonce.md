---
title: Развертывание приложений WCF с помощью ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: d733c6f523393737418c6394707c1d4e6e9c1710
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2018
ms.locfileid: "44365021"
---
# <a name="deploying-wcf-applications-with-clickonce"></a>Развертывание приложений WCF с помощью ClickOnce
Клиентские приложения, использующие Windows Communication Foundation (WCF) могут быть развернуты с помощью технологии ClickOnce. Эта технология позволяет им использовать преимущества средств защиты среды выполнения, предоставляемых управлением доступом для кода, если приложения снабжены цифровой подписью с надежным сертификатом. Сертификат, используемый для подписывания приложения ClickOnce, должен располагаться в хранилище надежных издателей, а локальная политика безопасности на клиентском компьютере должна быть настроена таким образом, чтобы предоставлять разрешения полного доверия приложениям, подписанным с использованием сертификата издателя.  
  
 Сведения о настройке приложений ClickOnce и надежных издателей, см. в разделе [Настройка надежных издателей ClickOnce](https://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о развертывании доверенных приложений](https://go.microsoft.com/fwlink/?LinkId=94775)  
 [Развертывание ClickOnce для Windows Forms в приложения](https://go.microsoft.com/fwlink/?LinkId=94776)
