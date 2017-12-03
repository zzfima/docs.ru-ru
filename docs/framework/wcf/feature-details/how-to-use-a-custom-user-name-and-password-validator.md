---
title: "Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля"
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
helpviewer_keywords: WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1ec4dc2d7f066d79b2cf54c3d474b47e769b626c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="890ba-102">Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="890ba-102">How to: Use a Custom User Name and Password Validator</span></span>
<span data-ttu-id="890ba-103">Когда для проверки подлинности используются имя пользователя и пароль, по умолчанию [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] использует Windows для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="890ba-103">By default, when a user name and password is used for authentication, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uses Windows to validate the user name and password.</span></span> <span data-ttu-id="890ba-104">Тем не менее [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет пользовательского имени и пароля схем проверки подлинности, также известный как *проверяющие элементы управления*.</span><span class="sxs-lookup"><span data-stu-id="890ba-104">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="890ba-105">Чтобы внедрить пользовательский проверяющий элемент управления для проверки подлинности имени пользователя и пароля, необходимо создать класс, унаследованный от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, и настроить его.</span><span class="sxs-lookup"><span data-stu-id="890ba-105">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>  
  
 <span data-ttu-id="890ba-106">Пример приложения см. в разделе [проверяющий элемент управления пароль для имени пользователя](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span><span class="sxs-lookup"><span data-stu-id="890ba-106">For a sample application, see [User Name Password Validator](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span></span>  
  
### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="890ba-107">Создание пользовательского проверяющего элемента управления для имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="890ba-107">To create a custom user name and password validator</span></span>  
  
1.  <span data-ttu-id="890ba-108">Создайте класс, наследующий от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="890ba-108">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2.  <span data-ttu-id="890ba-109">Реализуйте пользовательскую схему проверки подлинности, переопределив метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="890ba-109">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
     <span data-ttu-id="890ba-110">Не используйте код следующего примера, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде.</span><span class="sxs-lookup"><span data-stu-id="890ba-110">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="890ba-111">Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.</span><span class="sxs-lookup"><span data-stu-id="890ba-111">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>  
  
     <span data-ttu-id="890ba-112">Чтобы вернуть ошибки проверки подлинности клиенту, создайте исключение <xref:System.ServiceModel.FaultException> в методе <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="890ba-112">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="890ba-113">Настройка службы для использования пользовательского проверяющего элемента управления для проверки имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="890ba-113">To configure a service to use a custom user name and password validator</span></span>  
  
1.  <span data-ttu-id="890ba-114">Настройте привязку, использующую безопасность сообщений с любым транспортом или безопасность на уровне транспорта по HTTP(S).</span><span class="sxs-lookup"><span data-stu-id="890ba-114">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>  
  
     <span data-ttu-id="890ba-115">При использовании безопасности сообщений, добавьте одну из привязок, предоставляемых системой, такие как [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), или [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) безопасность сообщений поддерживает и `UserName` тип учетных данных.</span><span class="sxs-lookup"><span data-stu-id="890ba-115">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>  
  
     <span data-ttu-id="890ba-116">При использовании безопасности на уровне транспорта по HTTP (S), либо добавить [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) или [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \< netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) или [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , использующий HTTP (S) и `Basic` схему проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="890ba-116">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="890ba-117">Если используется платформа [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] или более поздняя версия, на уровне безопасности сообщений и транспорта можно применять пользовательский модуль проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="890ba-117">When [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] or later is used, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="890ba-118">Если используется платформа [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], пользовательский модуль проверки имени пользователя и пароля можно использовать только на уровне безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="890ba-118">With [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], a custom username and password validator can only be used with message security.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="890ba-119">Дополнительные сведения об использовании \<netTcpBinding > в этом контексте. в разделе [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="890ba-119">For more information on using \<netTcpBinding> in this context, see [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span></span>  
  
    1.  <span data-ttu-id="890ba-120">В файле конфигурации в разделе [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемента, добавьте [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="890ba-120">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
    2.  <span data-ttu-id="890ba-121">Добавить [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) или [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) элемент для раздела привязок.</span><span class="sxs-lookup"><span data-stu-id="890ba-121">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="890ba-122">Создание [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] элемент привязки в разделе [как: задание привязки службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="890ba-122"> creating an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
    3.  <span data-ttu-id="890ba-123">Задать `mode` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) или [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) для `Message`, `Transport`, `or``TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="890ba-123">Set the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, `or``TransportWithMessageCredential`.</span></span>  
  
    4.  <span data-ttu-id="890ba-124">Задать `clientCredentialType` атрибут [ \<сообщения >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) или [ \<транспорта >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="890ba-124">Set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>  
  
         <span data-ttu-id="890ba-125">При использовании безопасности сообщений, установить `clientCredentialType` атрибут [ \<сообщения >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) для `UserName`.</span><span class="sxs-lookup"><span data-stu-id="890ba-125">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>  
  
         <span data-ttu-id="890ba-126">При использовании безопасности на уровне транспорта по HTTP (S), установить `clientCredentialType` атрибут [ \<транспорта >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) или [ \<транспорта >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) для `Basic`.</span><span class="sxs-lookup"><span data-stu-id="890ba-126">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="890ba-127">Если служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] размещена на сервере служб IIS, на котором используется безопасность на уровне транспорта, а свойству <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> присвоено значение <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, в пользовательской схеме проверки подлинности используется подмножество возможностей проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="890ba-127">When a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="890ba-128">Это происходит потому, что в данном случае службы IIS выполняют проверку подлинности Windows перед вызовом службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] пользовательского модуля проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="890ba-128">That is because in this scenario, IIS performs Windows authentication prior to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invoking the custom authenticator.</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="890ba-129">Создание [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] элемент привязки в разделе [как: задание привязки службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="890ba-129"> creating an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
     <span data-ttu-id="890ba-130">В следующем примере показан код конфигурации для привязки.</span><span class="sxs-lookup"><span data-stu-id="890ba-130">The following example shows the configuration code for the binding.</span></span>  
  
    ```xml  
    <system.serviceModel>   
      <bindings>  
      <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="UserName" />  
            </security>  
          </binding>          
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
2.  <span data-ttu-id="890ba-131">Настройте поведение, которое будет указывать, что для проверки пар имени пользователя и пароля для входящих маркеров безопасности <xref:System.IdentityModel.Tokens.UserNameSecurityToken> будет использоваться пользовательский проверяющий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="890ba-131">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>  
  
    1.  <span data-ttu-id="890ba-132">Как дочерние для [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемента, добавьте [ \<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="890ba-132">As a child to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
    2.  <span data-ttu-id="890ba-133">Добавить [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) для [ \<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="890ba-133">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
    3.  <span data-ttu-id="890ba-134">Добавить [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) и присвойте `name` соответствующее значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="890ba-134">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
    4.  <span data-ttu-id="890ba-135">Добавить [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) для [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="890ba-135">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>  
  
    5.  <span data-ttu-id="890ba-136">Добавить [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) для [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="890ba-136">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
    6.  <span data-ttu-id="890ba-137">Присвойте свойству `userNamePasswordValidationMode` значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="890ba-137">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="890ba-138">Если значение `userNamePasswordValidationMode` не задано, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует проверку подлинности Windows вместо пользовательского проверяющего элемента управления для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="890ba-138">If the `userNamePasswordValidationMode` value is not set, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses Windows authentication instead of the custom user name and password validator.</span></span>  
  
    7.  <span data-ttu-id="890ba-139">Присвойте атрибуту `customUserNamePasswordValidatorType` значение типа вашего пользовательского проверяющего элемента управления для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="890ba-139">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>  
  
     <span data-ttu-id="890ba-140">В следующем примере показан фрагмент `<serviceCredentials>`, иллюстрирующий вышеуказанные действия.</span><span class="sxs-lookup"><span data-stu-id="890ba-140">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
    ```xml  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## <a name="example"></a><span data-ttu-id="890ba-141">Пример</span><span class="sxs-lookup"><span data-stu-id="890ba-141">Example</span></span>  
 <span data-ttu-id="890ba-142">В следующем примере кода показано, как создать пользовательский проверяющий элемент управления для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="890ba-142">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="890ba-143">Не используйте код, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде.</span><span class="sxs-lookup"><span data-stu-id="890ba-143">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="890ba-144">Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.</span><span class="sxs-lookup"><span data-stu-id="890ba-144">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="890ba-145">См. также</span><span class="sxs-lookup"><span data-stu-id="890ba-145">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>  
 [<span data-ttu-id="890ba-146">Как: использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="890ba-146">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 [<span data-ttu-id="890ba-147">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="890ba-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
