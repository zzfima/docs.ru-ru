---
title: Практическое руководство. Получение сертификата (WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 368401d91aa2a83110631d583660d6ccebf8d4fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491511"
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Практическое руководство. Получение сертификата (WCF)
Использовать Windows Communication Foundation (WCF) все возможности, используют сертификаты X.509, сначала нужно получить сертификаты.  
  
### <a name="to-obtain-an-x509-certificate"></a>Получение сертификата X.509  
  
1.  Выберите один из следующих вариантов.  
  
    -   Приобретите сертификат в центре сертификации, например VeriSign, Inc.  
  
    -   Создайте собственную службу сертификатов и настройте ее так, чтобы центр сертификации подписывал сертификаты. [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], Windows 2000 Server, Windows 2000 Server Datacenter и Windows 2000 Datacenter Server включают службы сертификатов, поддерживающие инфраструктуру открытых ключей (PKI). В Windows Server 2008 с помощью [служб сертификатов Active Directory](http://go.microsoft.com/fwlink/?LinkID=153483) роли для управления центром сертификации.  
  
    -   Создайте собственную службу сертификатов и не настраивайте подпись сертификатов.  
  
    > [!NOTE]
    >  Независимо от того, какой способ выбран, получатель запроса SOAP, который содержит сертификат X.509, должен доверять сертификату X.509. Это означает, что сертификат X.509 или издатель в цепи сертификатов находится в хранилище сертификатов "Доверенные лица" и сертификат X.509 не помещен в хранилище ненадежных сертификатов.  
  
## <a name="see-also"></a>См. также  
 [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Практическое руководство. Создание временных сертификатов для использования во время разработки](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
