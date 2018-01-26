---
title: "Практическое руководство. Получение сертификата (WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dcefa658aec37b9af3c4f9285ec76a0d549b868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Практическое руководство. Получение сертификата (WCF)
Чтобы воспользоваться какими-либо функциями [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], которые используют сертификаты X.509, сначала нужно получить сертификаты.  
  
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
