---
title: "Практическое руководство. Защита службы с использованием сертификата X.509"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 2d06c2aa-d0d7-4e5e-ad7e-77416aa1c10b
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e1ad7cd844ffbd3f45517f7d812ad3f5fa1ae3c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-secure-a-service-with-an-x509-certificate"></a><span data-ttu-id="d7ca5-102">Практическое руководство. Защита службы с использованием сертификата X.509</span><span class="sxs-lookup"><span data-stu-id="d7ca5-102">How to: Secure a Service with an X.509 Certificate</span></span>
<span data-ttu-id="d7ca5-103">Защита службы с помощью сертификата X.509 - стандартный прием, используемый в большинстве привязок [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7ca5-103">Securing a service with an X.509 certificate is a basic technique that most bindings in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] use.</span></span> <span data-ttu-id="d7ca5-104">В этом разделе описывается порядок настройки резидентной службы с сертификатом X.509.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-104">This topic walks through the steps of configuring a self-hosted service with an X.509 certificate.</span></span>  
  
 <span data-ttu-id="d7ca5-105">Предварительным условием является наличие действительного сертификата, который можно использовать для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-105">A prerequisite is a valid certificate that can be used to authenticate the server.</span></span> <span data-ttu-id="d7ca5-106">Сертификат должен быть выдан серверу доверенным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-106">The certificate must be issued to the server by a trusted certificate authority.</span></span> <span data-ttu-id="d7ca5-107">Если сертификат недействителен, ни один клиент, пытающийся воспользоваться службой, не будет доверять этой службе, следовательно, соединение установлено не будет.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-107">If the certificate is not valid, any client trying to use the service will not trust the service, and consequently no connection will be made.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d7ca5-108">с помощью сертификатов, в разделе [работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="d7ca5-108"> using certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
### <a name="to-configure-a-service-with-a-certificate-using-code"></a><span data-ttu-id="d7ca5-109">Настройка службы с сертификатом в коде</span><span class="sxs-lookup"><span data-stu-id="d7ca5-109">To configure a service with a certificate using code</span></span>  
  
1.  <span data-ttu-id="d7ca5-110">Создайте контракт службы и реализованную службу.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-110">Create the service contract and the implemented service.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="d7ca5-111">[Проектирование и реализация служб](../../../../docs/framework/wcf/designing-and-implementing-services.md).</span><span class="sxs-lookup"><span data-stu-id="d7ca5-111"> [Designing and Implementing Services](../../../../docs/framework/wcf/designing-and-implementing-services.md).</span></span>  
  
2.  <span data-ttu-id="d7ca5-112">Создайте экземпляр класса <xref:System.ServiceModel.WSHttpBinding> и установите для него режим безопасности <xref:System.ServiceModel.SecurityMode.Message>, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-112">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#1)]
     [!code-vb[C_SecureWithCertificate#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#1)]  
  
3.  <span data-ttu-id="d7ca5-113">Создайте две переменные типа <xref:System.Type>, по одной для типа контракта и реализованного контракта, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-113">Create two <xref:System.Type> variables, one each for the contract type and the implemented contract, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#2)]
     [!code-vb[C_SecureWithCertificate#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#2)]  
  
4.  <span data-ttu-id="d7ca5-114">Создайте экземпляр класса <xref:System.Uri> для базового адреса службы.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-114">Create an instance of the <xref:System.Uri> class for the base address of the service.</span></span> <span data-ttu-id="d7ca5-115">Поскольку привязка `WSHttpBinding` использует транспорт HTTP, универсальный код ресурса (URI) должен начинаться с соответствующей схемы; в противном случае при открытии службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] вызовет исключение.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-115">Because the `WSHttpBinding` uses the HTTP transport, the Uniform Resource Identifier (URI) must begin with that schema, or [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] will throw an exception when the service is opened.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#3)]
     [!code-vb[C_SecureWithCertificate#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#3)]  
  
5.  <span data-ttu-id="d7ca5-116">Создайте новый экземпляр класса <xref:System.ServiceModel.ServiceHost> с переменной реализованного контракта и URI.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-116">Create a new instance of the <xref:System.ServiceModel.ServiceHost> class with the implemented contract type variable and the URI.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#4)]
     [!code-vb[C_SecureWithCertificate#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#4)]  
  
6.  <span data-ttu-id="d7ca5-117">Добавьте в службу экземпляр класса <xref:System.ServiceModel.Description.ServiceEndpoint> с помощью метода <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-117">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> to the service using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span> <span data-ttu-id="d7ca5-118">Передайте контракт, привязку и адрес конечной точки конструктору, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-118">Pass the contract, binding, and an endpoint address to the constructor, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#5)]
     [!code-vb[C_SecureWithCertificate#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#5)]  
  
7.  <span data-ttu-id="d7ca5-119">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-119">Optional.</span></span> <span data-ttu-id="d7ca5-120">Чтобы извлекать метаданные из службы, создайте новый объект <xref:System.ServiceModel.Description.ServiceMetadataBehavior> и присвойте свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-120">To retrieve metadata from the service, create a new <xref:System.ServiceModel.Description.ServiceMetadataBehavior> object and set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#6)]
     [!code-vb[C_SecureWithCertificate#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#6)]  
  
8.  <span data-ttu-id="d7ca5-121">С помощью метода <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> добавьте в службу действительный сертификат.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-121">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to add the valid certificate to the service.</span></span> <span data-ttu-id="d7ca5-122">Для поиска сертификата в этом методе можно использовать один из нескольких способов.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-122">The method can use one of several methods to find a certificate.</span></span> <span data-ttu-id="d7ca5-123">В этом примере используется перечисление <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName>.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-123">This example uses the <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName> enumeration.</span></span> <span data-ttu-id="d7ca5-124">Это перечисление указывает, что переданное значение представляет собой имя сущности, которой был выдан сертификат.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-124">The enumeration specifies that the supplied value is the name of the entity that the certificate was issued to.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#7)]
     [!code-vb[C_SecureWithCertificate#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#7)]  
  
9. <span data-ttu-id="d7ca5-125">Вызовите метод <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>, чтобы служба начала прослушивание.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-125">Call the <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> method to start the service listening.</span></span> <span data-ttu-id="d7ca5-126">Если создается консольное приложение, вызовите метод <xref:System.Console.ReadLine%2A>, чтобы служба оставалась в состоянии прослушивания.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-126">If you are creating a console application, call the <xref:System.Console.ReadLine%2A> method to keep the service in the listening state.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#8)]
     [!code-vb[C_SecureWithCertificate#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="d7ca5-127">Пример</span><span class="sxs-lookup"><span data-stu-id="d7ca5-127">Example</span></span>  
 <span data-ttu-id="d7ca5-128">В следующем примере показана настройка службы с сертификатом X.509 с помощью метода <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-128">The following example uses the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method to configure a service with an X.509 certificate.</span></span>  
  
 [!code-csharp[C_SecureWithCertificate#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#9)]
 [!code-vb[C_SecureWithCertificate#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7ca5-129">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d7ca5-129">Compiling the Code</span></span>  
 <span data-ttu-id="d7ca5-130">Для компиляции кода требуются следующие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d7ca5-130">The following namespaces are required to compile the code:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.Web.Services.Description>  
  
-   <xref:System.Security.Cryptography.X509Certificates>  
  
-   <xref:System.Runtime.Serialization>  
  
## <a name="see-also"></a><span data-ttu-id="d7ca5-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d7ca5-131">See Also</span></span>  
 [<span data-ttu-id="d7ca5-132">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="d7ca5-132">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
