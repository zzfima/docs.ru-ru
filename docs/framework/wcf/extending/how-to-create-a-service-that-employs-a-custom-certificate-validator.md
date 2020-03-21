---
title: Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: af1bb9b2ff793f6e6854c1b253dd445a35a5076f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185575"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a><span data-ttu-id="cba6b-102">Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов</span><span class="sxs-lookup"><span data-stu-id="cba6b-102">How to: Create a Service that Employs a Custom Certificate Validator</span></span>
<span data-ttu-id="cba6b-103">В данном разделе показано, как реализовать пользовательский проверяющий элемент управления для сертификата и как настроить учетные данные клиента или службы, чтобы заменить логику проверки сертификата по умолчанию пользовательским проверяющим элементом управления для сертификата.</span><span class="sxs-lookup"><span data-stu-id="cba6b-103">This topic shows how to implement a custom certificate validator and how to configure client or service credentials to replace the default certificate validation logic with the custom certificate validator.</span></span>  
  
 <span data-ttu-id="cba6b-104">Если сертификат X.509 используется для проверки подлинности клиента или службы, Windows Communication Foundation (WCF) по умолчанию использует магазин сертификатов Windows и Crypto API для проверки сертификата и обеспечения его доверия.</span><span class="sxs-lookup"><span data-stu-id="cba6b-104">If the X.509 certificate is used to authenticate a client or service, Windows Communication Foundation (WCF) by default uses the Windows certificate store and Crypto API to validate the certificate and to ensure that it is trusted.</span></span> <span data-ttu-id="cba6b-105">Иногда встроенных функциональных возможностей проверки сертификатов недостаточно, их необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="cba6b-105">Sometimes the built-in certificate validation functionality is not enough and must be changed.</span></span> <span data-ttu-id="cba6b-106">WCF предоставляет простой способ изменить логику проверки, позволяя пользователям добавлять пользовательский валидатор сертификата.</span><span class="sxs-lookup"><span data-stu-id="cba6b-106">WCF provides an easy way to change the validation logic by allowing users to add a custom certificate validator.</span></span> <span data-ttu-id="cba6b-107">Если указан пользовательский валидатор сертификата, WCF не использует встроенную логику проверки сертификата, а полагается на пользовательский валидатор.</span><span class="sxs-lookup"><span data-stu-id="cba6b-107">If a custom certificate validator is specified, WCF does not use the built-in certificate validation logic but relies on the custom validator instead.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="cba6b-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="cba6b-108">Procedures</span></span>  
  
#### <a name="to-create-a-custom-certificate-validator"></a><span data-ttu-id="cba6b-109">Создание пользовательского проверяющего элемента управления для сертификата</span><span class="sxs-lookup"><span data-stu-id="cba6b-109">To create a custom certificate validator</span></span>  
  
1. <span data-ttu-id="cba6b-110">Определите новый производный класс на основе класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="cba6b-110">Define a new class derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span>  
  
2. <span data-ttu-id="cba6b-111">Реализуйте абстрактный метод <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="cba6b-111">Implement the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> method.</span></span> <span data-ttu-id="cba6b-112">Сертификат, который необходимо проверить, передается методу как аргумент.</span><span class="sxs-lookup"><span data-stu-id="cba6b-112">The certificate that must be validated is passed as an argument to the method.</span></span> <span data-ttu-id="cba6b-113">Если переданный сертификат недопустим согласно логике проверки, этот метод создает исключение <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span><span class="sxs-lookup"><span data-stu-id="cba6b-113">If the passed certificate is not valid according to the validation logic, this method throws a <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span></span> <span data-ttu-id="cba6b-114">Если сертификат действителен, метод возвращает его вызывающей стороне.</span><span class="sxs-lookup"><span data-stu-id="cba6b-114">If the certificate is valid, the method returns to the caller.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="cba6b-115">Чтобы вернуть ошибки проверки подлинности клиенту, создайте исключение <xref:System.ServiceModel.FaultException> в методе <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="cba6b-115">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a><span data-ttu-id="cba6b-116">Задание пользовательского проверяющего элемента управления для сертификата в конфигурации службы</span><span class="sxs-lookup"><span data-stu-id="cba6b-116">To specify a custom certificate validator in service configuration</span></span>  
  
1. <span data-ttu-id="cba6b-117">Добавьте [ \<в](../../configure-apps/file-schema/wcf/behaviors.md) [ \<элемент system.serviceModel](../../configure-apps/file-schema/wcf/system-servicemodel.md) [ \<>](../../configure-apps/file-schema/wcf/servicebehaviors.md)>></span><span class="sxs-lookup"><span data-stu-id="cba6b-117">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="cba6b-118">Добавьте [ \<поведение>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и установите `name` атрибут соответствующим значением.</span><span class="sxs-lookup"><span data-stu-id="cba6b-118">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="cba6b-119">Добавьте `<behavior>` [ \<>в элемент serviceCredentials.](../../configure-apps/file-schema/wcf/servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="cba6b-119">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the `<behavior>` element.</span></span>  
  
4. <span data-ttu-id="cba6b-120">Добавьте элемент `<clientCertificate>` в элемент `<serviceCredentials>`.</span><span class="sxs-lookup"><span data-stu-id="cba6b-120">Add a `<clientCertificate>` element to the `<serviceCredentials>` element.</span></span>  
  
5. <span data-ttu-id="cba6b-121">Добавьте [ \<>проверки подлинности](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) в `<clientCertificate>` элемент.</span><span class="sxs-lookup"><span data-stu-id="cba6b-121">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) to the `<clientCertificate>` element.</span></span>  
  
6. <span data-ttu-id="cba6b-122">Задайте для атрибута `customCertificateValidatorType` тип проверяющего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cba6b-122">Set the `customCertificateValidatorType` attribute to the validator type.</span></span> <span data-ttu-id="cba6b-123">В следующем примере для атрибута задано значение пространства имен и имени типа.</span><span class="sxs-lookup"><span data-stu-id="cba6b-123">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
7. <span data-ttu-id="cba6b-124">Задайте для атрибута `certificateValidationMode` значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="cba6b-124">Set the `certificateValidationMode` attribute to `Custom`.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="ServiceBehavior">  
         <serviceCredentials>  
          <clientCertificate>  
          <authentication certificateValidationMode="Custom" customCertificateValidatorType="Samples.MyValidator, service" />  
          </clientCertificate>  
         </serviceCredentials>  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a><span data-ttu-id="cba6b-125">Задание пользовательского проверяющего элемента управления для сертификата с использованием конфигурации на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="cba6b-125">To specify a custom certificate validator using configuration on the client</span></span>  
  
1. <span data-ttu-id="cba6b-126">Добавьте [ \<в](../../configure-apps/file-schema/wcf/behaviors.md) [ \<элемент system.serviceModel](../../configure-apps/file-schema/wcf/system-servicemodel.md) [ \<>](../../configure-apps/file-schema/wcf/servicebehaviors.md)>></span><span class="sxs-lookup"><span data-stu-id="cba6b-126">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="cba6b-127">Добавьте [ \<элемент endpointBehaviors>.](../../configure-apps/file-schema/wcf/endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="cba6b-127">Add an [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) element.</span></span>  
  
3. <span data-ttu-id="cba6b-128">Добавьте элемент `<behavior>` и присвойте атрибуту `name` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="cba6b-128">Add a `<behavior>` element and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="cba6b-129">Добавьте [ \<элемент clientCredentials>.](../../configure-apps/file-schema/wcf/clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="cba6b-129">Add a [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
5. <span data-ttu-id="cba6b-130">Добавить [ \<сервисный сертификат>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="cba6b-130">Add a [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span></span>  
  
6. <span data-ttu-id="cba6b-131">Добавьте [ \<>аутентификации,](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) показанную в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="cba6b-131">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) as shown on the following example.</span></span>  
  
7. <span data-ttu-id="cba6b-132">Задайте для атрибута `customCertificateValidatorType` тип проверяющего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cba6b-132">Set the `customCertificateValidatorType` attribute to the validator type.</span></span>  
  
8. <span data-ttu-id="cba6b-133">Задайте для атрибута `certificateValidationMode` значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="cba6b-133">Set the `certificateValidationMode` attribute to `Custom`.</span></span> <span data-ttu-id="cba6b-134">В следующем примере для атрибута задано значение пространства имен и имени типа.</span><span class="sxs-lookup"><span data-stu-id="cba6b-134">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <endpointBehaviors>  
        <behavior name="clientBehavior">  
         <clientCredentials>  
          <serviceCertificate>  
           <authentication certificateValidationMode="Custom"
                  customCertificateValidatorType=  
             "Samples.CustomX509CertificateValidator, client"/>  
          </serviceCertificate>  
         </clientCredentials>  
        </behavior>  
       </endpointBehaviors>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a><span data-ttu-id="cba6b-135">Задание пользовательского проверяющего элемента управления для сертификата с использованием кода на стороне службы</span><span class="sxs-lookup"><span data-stu-id="cba6b-135">To specify a custom certificate validator using code on the service</span></span>  
  
1. <span data-ttu-id="cba6b-136">Задайте пользовательский проверяющий элемент управления для сертификата в свойстве <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>.</span><span class="sxs-lookup"><span data-stu-id="cba6b-136">Specify the custom certificate validator on the <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> property.</span></span> <span data-ttu-id="cba6b-137">Получить доступ к учетным данным службы можно с помощью свойства <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.</span><span class="sxs-lookup"><span data-stu-id="cba6b-137">You can access the service credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span>  
  
2. <span data-ttu-id="cba6b-138">Установите свойство <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> в значение <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="cba6b-138">Set the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a><span data-ttu-id="cba6b-139">Задание пользовательского проверяющего элемента управления для сертификата с использованием кода на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="cba6b-139">To specify a custom certificate validator using code on the client</span></span>  
  
1. <span data-ttu-id="cba6b-140">Задайте пользовательский проверяющий элемент управления для сертификата в свойстве <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>.</span><span class="sxs-lookup"><span data-stu-id="cba6b-140">Specify the custom certificate validator using the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> property.</span></span> <span data-ttu-id="cba6b-141">Получить доступ к учетным данным клиента можно с помощью свойства <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.</span><span class="sxs-lookup"><span data-stu-id="cba6b-141">You can access the client credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span> <span data-ttu-id="cba6b-142">(Клиентский класс, генерируемый [ServiceModel Metadata Utility Tool (Svcutil.exe),](../servicemodel-metadata-utility-tool-svcutil-exe.md) всегда происходит от <xref:System.ServiceModel.ClientBase%601> класса.)</span><span class="sxs-lookup"><span data-stu-id="cba6b-142">(The client class generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) always derives from the <xref:System.ServiceModel.ClientBase%601> class.)</span></span>  
  
2. <span data-ttu-id="cba6b-143">Установите свойство <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> в значение <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="cba6b-143">Set the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cba6b-144">Пример</span><span class="sxs-lookup"><span data-stu-id="cba6b-144">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cba6b-145">Описание</span><span class="sxs-lookup"><span data-stu-id="cba6b-145">Description</span></span>  
 <span data-ttu-id="cba6b-146">В следующем примере показана реализация пользовательского проверяющего элемента управления для сертификата и его использование на стороне службы.</span><span class="sxs-lookup"><span data-stu-id="cba6b-146">The following sample shows an implementation of a custom certificate validator and its usage on the service.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cba6b-147">Код</span><span class="sxs-lookup"><span data-stu-id="cba6b-147">Code</span></span>  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="cba6b-148">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cba6b-148">See also</span></span>

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
