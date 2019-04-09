---
title: Практическое руководство. Защита службы с использованием сертификата X.509
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d06c2aa-d0d7-4e5e-ad7e-77416aa1c10b
ms.openlocfilehash: 6757d6375cbe1662b8bd7beb8a7562be166bc414
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181510"
---
# <a name="how-to-secure-a-service-with-an-x509-certificate"></a>Практическое руководство. Защита службы с использованием сертификата X.509
Защита службы с использованием сертификата X.509 является базовый метод, используемый в большинстве привязок в Windows Communication Foundation (WCF). В этом разделе описывается порядок настройки резидентной службы с сертификатом X.509.  
  
 Предварительным условием является наличие действительного сертификата, который можно использовать для проверки подлинности сервера. Сертификат должен быть выдан серверу доверенным центром сертификации. Если сертификат недействителен, ни один клиент, пытающийся воспользоваться службой, не будет доверять этой службе, следовательно, соединение установлено не будет. Дополнительные сведения об использовании сертификатов см. в разделе [работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
### <a name="to-configure-a-service-with-a-certificate-using-code"></a>Настройка службы с сертификатом в коде  
  
1.  Создайте контракт службы и реализованную службу. Дополнительные сведения см. в разделе [проектирование и реализация служб](../../../../docs/framework/wcf/designing-and-implementing-services.md).  
  
2.  Создайте экземпляр класса <xref:System.ServiceModel.WSHttpBinding> и установите для него режим безопасности <xref:System.ServiceModel.SecurityMode.Message>, как показано в следующем коде.  
  
     [!code-csharp[C_SecureWithCertificate#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#1)]
     [!code-vb[C_SecureWithCertificate#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#1)]  
  
3.  Создайте две переменные типа <xref:System.Type>, по одной для типа контракта и реализованного контракта, как показано в следующем коде.  
  
     [!code-csharp[C_SecureWithCertificate#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#2)]
     [!code-vb[C_SecureWithCertificate#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#2)]  
  
4.  Создайте экземпляр класса <xref:System.Uri> для базового адреса службы. Так как `WSHttpBinding` использует транспорт HTTP, универсальный код ресурса (URI) должен начинаться с соответствующей схемы, или Windows Communication Foundation (WCF) приведет к возникновению исключения при открытии службы.  
  
     [!code-csharp[C_SecureWithCertificate#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#3)]
     [!code-vb[C_SecureWithCertificate#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#3)]  
  
5.  Создайте новый экземпляр класса <xref:System.ServiceModel.ServiceHost> с переменной реализованного контракта и URI.  
  
     [!code-csharp[C_SecureWithCertificate#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#4)]
     [!code-vb[C_SecureWithCertificate#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#4)]  
  
6.  Добавьте в службу экземпляр класса <xref:System.ServiceModel.Description.ServiceEndpoint> с помощью метода <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>. Передайте контракт, привязку и адрес конечной точки конструктору, как показано в следующем коде.  
  
     [!code-csharp[C_SecureWithCertificate#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#5)]
     [!code-vb[C_SecureWithCertificate#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#5)]  
  
7.  Необязательный параметр. Чтобы извлекать метаданные из службы, создайте новый объект <xref:System.ServiceModel.Description.ServiceMetadataBehavior> и присвойте свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> значение `true`.  
  
     [!code-csharp[C_SecureWithCertificate#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#6)]
     [!code-vb[C_SecureWithCertificate#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#6)]  
  
8.  С помощью метода <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> добавьте в службу действительный сертификат. Для поиска сертификата в этом методе можно использовать один из нескольких способов. В этом примере используется перечисление <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName>. Это перечисление указывает, что переданное значение представляет собой имя сущности, которой был выдан сертификат.  
  
     [!code-csharp[C_SecureWithCertificate#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#7)]
     [!code-vb[C_SecureWithCertificate#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#7)]  
  
9. Вызовите метод <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>, чтобы служба начала прослушивание. Если создается консольное приложение, вызовите метод <xref:System.Console.ReadLine%2A>, чтобы служба оставалась в состоянии прослушивания.  
  
     [!code-csharp[C_SecureWithCertificate#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#8)]
     [!code-vb[C_SecureWithCertificate#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#8)]  
  
## <a name="example"></a>Пример  
 В следующем примере показана настройка службы с сертификатом X.509 с помощью метода <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>.  
  
 [!code-csharp[C_SecureWithCertificate#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#9)]
 [!code-vb[C_SecureWithCertificate#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#9)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для компиляции кода требуются следующие пространства имен.  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.Web.Services.Description>  
  
-   <xref:System.Security.Cryptography.X509Certificates>  
  
-   <xref:System.Runtime.Serialization>  
  
## <a name="see-also"></a>См. также

- [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
