---
title: Развертывание приложений WCF с помощью ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: ceb652eed1a7cc377538f5d693dcb85ed99da4b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456700"
---
# <a name="deploying-wcf-applications-with-clickonce"></a>Развертывание приложений WCF с помощью ClickOnce
Клиентские приложения, использующие Windows Communication Foundation (WCF) могут быть развернуты с помощью технологии ClickOnce. Эта технология позволяет им использовать преимущества средств защиты среды выполнения, предоставляемых управлением доступом для кода, если приложения снабжены цифровой подписью с надежным сертификатом. Сертификат, используемый для подписывания приложения ClickOnce, должен располагаться в хранилище надежных издателей, а локальная политика безопасности на клиентском компьютере должна быть настроена таким образом, чтобы предоставлять разрешения полного доверия приложениям, подписанным с использованием сертификата издателя.  
  
 Сведения о настройке приложения ClickOnce и доверенных издателей см. в разделе [Настройка надежных издателей ClickOnce](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о развертывании доверенных приложений](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [Развертывание ClickOnce для Windows Forms приложений](http://go.microsoft.com/fwlink/?LinkId=94776)
