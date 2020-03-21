---
title: Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], validation differences
ms.assetid: 953a219f-4745-4019-9894-c70704f352e6
ms.openlocfilehash: 0e82d1898bec7cda474a5a92958b5af1b30c9de7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185410"
---
# <a name="certificate-validation-differences-between-https-ssl-over-tcp-and-soap-security"></a>Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP
Вы можете использовать сертификаты в Windows Communication Foundation (WCF) с безопасностью на уровне сообщений (SOAP) в дополнение к безопасности транспортного слоя (TLS) по сравнению с HTTP (HTTPS) или TCP. В данном разделе описываются различия в способе, который используется для проверки сертификатов.  
  
## <a name="validation-of-https-client-certificates"></a>Проверка сертификатов клиента HTTPS  
 При использовании HTTPS для связи клиента и службы сертификат, который клиент использует для проверки подлинности службы, должен поддерживать цепь доверия. То есть, сертификат должен связываться по цепочке с доверенным корневым центром сертификации. Если нет, то слой <xref:System.Net.WebException> HTTP поднимает сообщение "Удаленный сервер вернул ошибку: (403) Запрещено". WCF всплывает на <xref:System.ServiceModel.Security.MessageSecurityException>поверхность этого исключения как .  
  
## <a name="validation-of-https-service-certificates"></a>Проверка сертификатов службы HTTPS  
 При использовании HTTPS для связи клиента и службы сертификат, используемый сервером для проверки подлинности службы, должен поддерживать цепь доверия. То есть, сертификат должен связываться по цепочке с доверенным корневым центром сертификации. Для проверки отмены сертификата проверка в сети не выполняется. Данное поведение можно переопределить, зарегистрировав обратный звонок <xref:System.Net.Security.RemoteCertificateValidationCallback>, как показано в следующем коде.  
  
 [!code-csharp[c_CertificateValidationDifferences#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#1)]
 [!code-vb[c_CertificateValidationDifferences#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#1)]  
  
 где подписывание `ValidateServerCertificate` показано ниже:  
  
 [!code-csharp[c_CertificateValidationDifferences#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#2)]
 [!code-vb[c_CertificateValidationDifferences#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#2)]  
  
 Реализация `ValidateServerCertificate` может выполнить любые проверки, которые разработчик приложения-клиента сочтет необходимыми для проверки сертификата службы.  
  
## <a name="validation-of-client-certificates-in-ssl-over-tcp-or-soap-security"></a>Проверка сертификатов клиента в SSL по TCP или механизме безопасности SOAP  
 При использовании протокола SSL по TCP или безопасности SOAP сертификаты клиента проверяются в соответствии со значением свойства <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> класса <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>. Свойство установлено в одно из значений <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Проверка отзыва сертификатов выполняется в соответствии со значениями свойства <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A> класса <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>. Свойство установлено в одно из значений <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.  
  
 [!code-csharp[c_CertificateValidationDifferences#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#3)]
 [!code-vb[c_CertificateValidationDifferences#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#3)]  
  
## <a name="validation-of-service-certificate-in-ssl-over-tcp-and-soap-security"></a>Проверка сертификатов службы в SSL по TCP или механизме безопасности SOAP  
 При использовании протокола SSL по TCP или безопасности SOAP сертификаты службы проверяются в соответствии со значением свойства <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> класса <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>. Свойство установлено в одно из значений <xref:System.ServiceModel.Security.X509CertificateValidationMode>.  
  
 Проверка отзыва сертификатов выполняется в соответствии со значениями свойства <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A> класса <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>. Свойство установлено в одно из значений <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.  
  
 [!code-csharp[c_CertificateValidationDifferences#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#4)]
 [!code-vb[c_CertificateValidationDifferences#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#4)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.Security.RemoteCertificateValidationCallback>
- [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
