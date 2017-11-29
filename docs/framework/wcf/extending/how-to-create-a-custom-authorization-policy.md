---
title: "Практическое руководство. Создание пользовательской политики авторизации"
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
ms.assetid: 05b0549b-882d-4660-b6f0-5678543e5475
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8a4a458d49e7ec3db3e80202e53e3a1f264d207b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-authorization-policy"></a><span data-ttu-id="2a9d0-102">Практическое руководство. Создание пользовательской политики авторизации</span><span class="sxs-lookup"><span data-stu-id="2a9d0-102">How to: Create a Custom Authorization Policy</span></span>
<span data-ttu-id="2a9d0-103">Инфраструктура модели удостоверения в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] поддерживает модель авторизации, основанную на утверждениях.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-103">The Identity Model infrastructure in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] supports a claim-based authorization model.</span></span> <span data-ttu-id="2a9d0-104">Утверждения извлекаются из маркеров, дополнительно обрабатываемых пользовательской политикой авторизации, и затем помещаются в контекст <xref:System.IdentityModel.Policy.AuthorizationContext>, который позже может проверяться для принятия решений по авторизации.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-104">Claims are extracted from tokens, optionally processed by custom authorization policy, and then placed into an <xref:System.IdentityModel.Policy.AuthorizationContext> that can then be examined to make authorization decisions.</span></span> <span data-ttu-id="2a9d0-105">Пользовательская политика может использоваться для преобразования утверждений из входящих маркеров в утверждения, ожидаемые приложением.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-105">A custom policy can be used to transform claims from incoming tokens into claims expected by the application.</span></span> <span data-ttu-id="2a9d0-106">Таким образом, прикладной уровень может быть изолирован от сведений различных утверждений, обслуживаемых разными типами маркеров, которые поддерживаются системой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a9d0-106">In this way, the application layer can be insulated from the details on the differing claims served up by the different token types that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports.</span></span> <span data-ttu-id="2a9d0-107">В данном разделе показываются реализация пользовательской политики авторизации и добавление этой политики в коллекцию политик, используемых службой.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-107">This topic shows how to implement a custom authorization policy and how to add that policy to the collection of policies used by a service.</span></span>  
  
### <a name="to-implement-a-custom-authorization-policy"></a><span data-ttu-id="2a9d0-108">Реализация пользовательской политики авторизации</span><span class="sxs-lookup"><span data-stu-id="2a9d0-108">To implement a custom authorization policy</span></span>  
  
1.  <span data-ttu-id="2a9d0-109">Определите новый класс, наследуемый от <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-109">Define a new class that derives from <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>  
  
2.  <span data-ttu-id="2a9d0-110">Реализуйте предназначенное только для чтения свойство <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> посредством создания уникальной строки в конструкторе для данного класса и возврата этой строки при каждом доступе к данному свойству.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-110">Implement the read-only <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> property by generating a unique string in the constructor for the class and returning that string whenever the property is accessed.</span></span>  
  
3.  <span data-ttu-id="2a9d0-111">Реализуйте предназначенное только для чтения свойство <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> посредством возврата набора <xref:System.IdentityModel.Claims.ClaimSet>, представляющего поставщика политики.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-111">Implement the read-only <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> property by returning a <xref:System.IdentityModel.Claims.ClaimSet> that represents the policy issuer.</span></span> <span data-ttu-id="2a9d0-112">Это может быть набор `ClaimSet`, который представляет приложение, или встроенный набор `ClaimSet` (например, набор `ClaimSet`, возвращаемый статическим свойством <xref:System.IdentityModel.Claims.ClaimSet.System%2A>).</span><span class="sxs-lookup"><span data-stu-id="2a9d0-112">This could be a `ClaimSet` that represents the application or a built-in `ClaimSet` (for example, the `ClaimSet` returned by the static <xref:System.IdentityModel.Claims.ClaimSet.System%2A> property.</span></span>  
  
4.  <span data-ttu-id="2a9d0-113">Реализуйте метод <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> согласно описанию в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-113">Implement the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method as described in the following procedure.</span></span>  
  
### <a name="to-implement-the-evaluate-method"></a><span data-ttu-id="2a9d0-114">Реализация метода Evaluate</span><span class="sxs-lookup"><span data-stu-id="2a9d0-114">To implement the Evaluate method</span></span>  
  
1.  <span data-ttu-id="2a9d0-115">В этот метод передаются два параметра: экземпляр класса <xref:System.IdentityModel.Policy.EvaluationContext> и ссылка на объект.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-115">Two parameters are passed to this method: an instance of the <xref:System.IdentityModel.Policy.EvaluationContext> class and an object reference.</span></span>  
  
2.  <span data-ttu-id="2a9d0-116">Если пользовательская политика авторизации добавляет <xref:System.IdentityModel.Claims.ClaimSet> экземпляров независимо от текущего содержимого класса <xref:System.IdentityModel.Policy.EvaluationContext>, добавьте каждый `ClaimSet` путем вызова <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> метода и возврата `true` из <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-116">If the custom authorization policy adds <xref:System.IdentityModel.Claims.ClaimSet> instances without regard to the current content of the <xref:System.IdentityModel.Policy.EvaluationContext>, then add each `ClaimSet` by calling the <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> method and return `true` from the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> method.</span></span> <span data-ttu-id="2a9d0-117">Возврат значения `true` указывает инфраструктуре авторизации, что политика авторизации выполнила свою работу и снова ее вызывать не требуется.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-117">Returning `true` indicates to the authorization infrastructure that the authorization policy has performed its work and does not need to be called again.</span></span>  
  
3.  <span data-ttu-id="2a9d0-118">Если пользовательская политика авторизации добавляет наборы утверждений только в случае наличия определенных утверждений в классе `EvaluationContext`, выполните поиск этих утверждений, проверив экземпляры `ClaimSet`, возвращенные свойством <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-118">If the custom authorization policy adds claim sets only if certain claims are already present in the `EvaluationContext`, then look for those claims by examining the `ClaimSet` instances returned by the <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A> property.</span></span> <span data-ttu-id="2a9d0-119">Если утверждения присутствуют, добавьте новые наборы утверждений, вызвав метод <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29>, и в случае отсутствия необходимости добавления дополнительных наборов утверждений верните значение `true`, указывающее инфраструктуре авторизации, что политика авторизации завершила свою работу.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-119">If the claims are present, then add the new claim sets by calling the <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> method and, if no more claim sets are to be added, return `true`, indicating to the authorization infrastructure that the authorization policy has completed its work.</span></span> <span data-ttu-id="2a9d0-120">Если утверждения отсутствуют, верните значение `false`, указывающее, что в случае добавления дополнительных наборов утверждений в класс `EvaluationContext` другими политиками авторизации политика авторизации должна быть вызвана снова.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-120">If the claims are not present, return `false`, indicating that the authorization policy should be called again if other authorization policies add more claim sets to the `EvaluationContext`.</span></span>  
  
4.  <span data-ttu-id="2a9d0-121">В более сложных сценариях обработки второй параметр метода <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> используется для хранения переменной состояния, которую инфраструктура авторизации будет передавать назад в течение каждого последующего вызова метода <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> для конкретной оценки.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-121">In more complex processing scenarios, the second parameter of the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method is used to store a state variable that the authorization infrastructure will pass back during each subsequent call to the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method for a particular evaluation.</span></span>  
  
### <a name="to-specify-a-custom-authorization-policy-through-configuration"></a><span data-ttu-id="2a9d0-122">Задание пользовательской политики авторизации с помощью конфигурации</span><span class="sxs-lookup"><span data-stu-id="2a9d0-122">To specify a custom authorization policy through configuration</span></span>  
  
1.  <span data-ttu-id="2a9d0-123">Задайте тип пользовательской политики авторизации с помощью атрибута `policyType` в элементе `add` элемента `authorizationPolicies` в элементе `serviceAuthorization`.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-123">Specify the type of the custom authorization policy in the `policyType` attribute in the `add` element in the `authorizationPolicies` element in the `serviceAuthorization` element.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
        <serviceAuthorization serviceAuthorizationManagerType=  
                  "Samples.MyServiceAuthorizationManager" >  
          <authorizationPolicies>         
            <add policyType="Samples.MyAuthorizationPolicy"  
          </authorizationPolicies>  
        </serviceAuthorization>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-specify-a-custom-authorization-policy-through-code"></a><span data-ttu-id="2a9d0-124">Задание пользовательской политики авторизации с помощью кода</span><span class="sxs-lookup"><span data-stu-id="2a9d0-124">To specify a custom authorization policy through code</span></span>  
  
1.  <span data-ttu-id="2a9d0-125">Создайте список <xref:System.Collections.Generic.List%601> политики <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-125">Create a <xref:System.Collections.Generic.List%601> of <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>  
  
2.  <span data-ttu-id="2a9d0-126">Создайте экземпляр пользовательской политики авторизации.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-126">Create an instance of the custom authorization policy.</span></span>  
  
3.  <span data-ttu-id="2a9d0-127">Добавьте экземпляр политики авторизации в список.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-127">Add the authorization policy instance to the list.</span></span>  
  
4.  <span data-ttu-id="2a9d0-128">Повторите шаги 2 и 3 для каждой пользовательской политики авторизации.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-128">Repeat steps 2 and 3 for each custom authorization policy.</span></span>  
  
5.  <span data-ttu-id="2a9d0-129">Присвойте предназначенную только для чтения версию списка свойству <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-129">Assign a read-only version of the list to the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A> property.</span></span>  
  
     [!code-csharp[c_CustomAuthPol#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#8)]
     [!code-vb[c_CustomAuthPol#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="2a9d0-130">Пример</span><span class="sxs-lookup"><span data-stu-id="2a9d0-130">Example</span></span>  
 <span data-ttu-id="2a9d0-131">В следующем примере показана полная реализация <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span><span class="sxs-lookup"><span data-stu-id="2a9d0-131">The following example shows a complete <xref:System.IdentityModel.Policy.IAuthorizationPolicy> implementation.</span></span>  
  
 [!code-csharp[c_CustomAuthPol#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#5)]
 [!code-vb[c_CustomAuthPol#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="2a9d0-132">См. также</span><span class="sxs-lookup"><span data-stu-id="2a9d0-132">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [<span data-ttu-id="2a9d0-133">Как: сравнение утверждений</span><span class="sxs-lookup"><span data-stu-id="2a9d0-133">How to: Compare Claims</span></span>](../../../../docs/framework/wcf/extending/how-to-compare-claims.md)  
 [<span data-ttu-id="2a9d0-134">Как: Создание пользовательского диспетчера авторизации для службы</span><span class="sxs-lookup"><span data-stu-id="2a9d0-134">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="2a9d0-135">Политика авторизации</span><span class="sxs-lookup"><span data-stu-id="2a9d0-135">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)
