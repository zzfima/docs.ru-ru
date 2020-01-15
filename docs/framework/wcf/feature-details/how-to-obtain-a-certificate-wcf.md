---
title: Практическое руководство. Получение сертификата (WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: bfe6dcfe6850ee17a7bbb59f3a6ccad6c3c3e7d7
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964242"
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Практическое руководство. Получение сертификата (WCF)
Чтобы использовать любую из функций Windows Communication Foundation (WCF), использующих сертификаты X. 509, сначала нужно получить сертификаты.  
  
### <a name="to-obtain-an-x509-certificate"></a>Получение сертификата X.509  
  
1. Выберите один из следующих вариантов.  
  
    - Приобретите сертификат в центре сертификации, например VeriSign, Inc.  
  
    - Создайте собственную службу сертификатов и настройте ее так, чтобы центр сертификации подписывал сертификаты. Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter и Windows 2000 Datacenter Server включают службы сертификации, поддерживающие инфраструктуру открытых ключей (PKI). В Windows Server 2008 для управления центром сертификации используется [Active Directory роль служб сертификации](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) .  
  
    - Создайте собственную службу сертификатов и не настраивайте подпись сертификатов.  
  
    > [!NOTE]
    > Независимо от того, какой способ выбран, получатель запроса SOAP, который содержит сертификат X.509, должен доверять сертификату X.509. Это означает, что сертификат X.509 или издатель в цепи сертификатов находится в хранилище сертификатов "Доверенные лица" и сертификат X.509 не помещен в хранилище ненадежных сертификатов.  
  
## <a name="see-also"></a>См. также:

- [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Практическое руководство. Создание временных сертификатов для использования во время разработки](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
