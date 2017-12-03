---
title: "Практическое руководство. Извлечение отпечатка сертификата"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: certificates [WCF], retrieving thumbprint
ms.assetid: da3101aa-78cd-4c34-9652-d1f24777eeab
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45f66a7003fe712ab482d5237762e2bafffc5a6e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-retrieve-the-thumbprint-of-a-certificate"></a>Практическое руководство. Извлечение отпечатка сертификата
При написании приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] , использующего для проверки подлинности сертификат X.509, часто возникает необходимость задать утверждения из сертификата Например, при использовании перечисления <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> в методе <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> необходимо указать утверждение отпечатка. Чтобы найти значение утверждения, необходимо выполнить два действия. Сначала необходимо открыть оснастку сертификатов консоли управления (MMC). (См. раздел [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)). После этого, как описано в этом разделе, необходимо найти соответствующий сертификат и скопировать его отпечаток (или другие значения утверждений).  
  
 Если сертификат используется для проверки подлинности службы, важно запомнить значение столбца **Кому выдан** (первый столбец консоли). При использовании для защиты транспорта протокола SSL одним из первых шагов является сравнение базового адреса универсального кода ресурса (URI) службы со значением поля **Кому выдан** . Значения должны совпадать, в противном случае процесс проверки подлинности будет прерван.  
  
 Кроме того, можно с помощью средства Makecert.exe из пакета SDK для [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] создать временные сертификаты для использования только на этапе разработки. Однако по умолчанию такой сертификат не выдается центром сертификации и не может использоваться в рабочей среде. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Как: создание временных сертификатов для использования во время разработки](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).  
  
### <a name="to-retrieve-a-certificates-thumbprint"></a>Извлечение отпечатка сертификата  
  
1.  Откройте оснастку "Сертификаты" консоли управления (MMC). (См. раздел [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)).  
  
2.  В левой области окна **Корень консоли** щелкните узел **Сертификаты (локальный компьютер)**.  
  
3.  Щелкните папку **Личные** , чтобы развернуть ее.  
  
4.  Щелкните папку **Сертификаты** , чтобы развернуть ее.  
  
5.  В списке сертификатов найдите заголовок **Назначения** . Найдите сертификат, назначением которого является **Проверка подлинности клиента** .  
  
6.  Дважды щелкните сертификат.  
  
7.  В диалоговом окне **Сертификат** перейдите на вкладку **Состав** .  
  
8.  Найдите в списке поле **Отпечаток**и щелкните его.  
  
9. Скопируйте шестнадцатеричные значения из текстового поля. Если этот отпечаток используется в коде `X509FindType`, удалите пробелы между шестнадцатеричными значениями. Например, отпечаток "a9 09 50 2d d8 2a e4 14 33 e6 f8 38 86 b0 0d 42 77 a3 2a 7b" необходимо задавать в коде в виде "a909502dd82ae41433e6f83886b00d4277a32a7b".  
  
## <a name="see-also"></a>См. также  
 <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>  
 [Как: Настройка порта с SSL-сертификата](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [Как: Просмотр сертификатов с помощью оснастки MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [Как: создание временных сертификатов для использования во время разработки](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
