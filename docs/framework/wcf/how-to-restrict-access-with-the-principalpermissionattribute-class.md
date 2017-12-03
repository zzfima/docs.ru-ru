---
title: "Практическое руководство. Ограничение доступа с использованием класса PrincipalPermissionAttribute"
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
helpviewer_keywords:
- PrincipalPermissionAttribute class
- WCF, authorization
- WCF, security
ms.assetid: 5162f5c4-8781-4cc4-9425-bb7620eaeaf4
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ddfb7b343bf4eb551b5029c538d29f104698adf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-restrict-access-with-the-principalpermissionattribute-class"></a><span data-ttu-id="8c930-102">Практическое руководство. Ограничение доступа с использованием класса PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="8c930-102">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>
<span data-ttu-id="8c930-103">Управление доступом к ресурсам компьютера Windows-домена - это базовая задача обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="8c930-103">Controlling the access to resources on a Windows-domain computer is a basic security task.</span></span> <span data-ttu-id="8c930-104">Например, только определенные пользователи должны иметь возможность просматривать конфиденциальные данные, такие как платежные ведомости.</span><span class="sxs-lookup"><span data-stu-id="8c930-104">For example, only certain users should be able to view sensitive data, such as payroll information.</span></span> <span data-ttu-id="8c930-105">В этом разделе рассматривается, как ограничить доступ к методу, потребовав, чтобы пользователь принадлежал к заранее заданной группе.</span><span class="sxs-lookup"><span data-stu-id="8c930-105">This topic explains how to restrict access to a method by demanding that the user belong to a predefined group.</span></span> <span data-ttu-id="8c930-106">Работающий пример см. в разделе [авторизации доступа к операциям службы](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md).</span><span class="sxs-lookup"><span data-stu-id="8c930-106">For a working sample, see [Authorizing Access to Service Operations](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md).</span></span>  
  
 <span data-ttu-id="8c930-107">Эта задача состоит из двух отдельных процедур.</span><span class="sxs-lookup"><span data-stu-id="8c930-107">The task consists of two separate procedures.</span></span> <span data-ttu-id="8c930-108">Первая создает группу и заносит в нее пользователей.</span><span class="sxs-lookup"><span data-stu-id="8c930-108">The first creates the group and populates it with users.</span></span> <span data-ttu-id="8c930-109">Вторая применяет класс <xref:System.Security.Permissions.PrincipalPermissionAttribute>, чтобы задать группу.</span><span class="sxs-lookup"><span data-stu-id="8c930-109">The second applies the <xref:System.Security.Permissions.PrincipalPermissionAttribute> class to specify the group.</span></span>  
  
### <a name="to-create-a-windows-group"></a><span data-ttu-id="8c930-110">Создание группы Windows</span><span class="sxs-lookup"><span data-stu-id="8c930-110">To create a Windows group</span></span>  
  
1.  <span data-ttu-id="8c930-111">Откройте **Управление компьютером** консоли.</span><span class="sxs-lookup"><span data-stu-id="8c930-111">Open the **Computer Management** console.</span></span>  
  
2.  <span data-ttu-id="8c930-112">На левой панели щелкните **локальные пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="8c930-112">In the left panel, click **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="8c930-113">Щелкните правой кнопкой мыши **группы**и нажмите кнопку **новая группа**.</span><span class="sxs-lookup"><span data-stu-id="8c930-113">Right-click **Groups**, and click **New Group**.</span></span>  
  
4.  <span data-ttu-id="8c930-114">В **имя группы** введите имя для новой группы.</span><span class="sxs-lookup"><span data-stu-id="8c930-114">In the **Group Name** box, type a name for the new group.</span></span>  
  
5.  <span data-ttu-id="8c930-115">В **описание** введите описание новой группы.</span><span class="sxs-lookup"><span data-stu-id="8c930-115">In the **Description** box, type a description of the new group.</span></span>  
  
6.  <span data-ttu-id="8c930-116">Нажмите кнопку **добавить** кнопку, чтобы добавить в группу новых членов.</span><span class="sxs-lookup"><span data-stu-id="8c930-116">Click the **Add** button to add new members to the group.</span></span>  
  
7.  <span data-ttu-id="8c930-117">Если вы добавили себя в группу и хотите протестировать приведенный ниже код, необходимо выйти из системы и снова войти в нее, чтобы быть включенным в группу.</span><span class="sxs-lookup"><span data-stu-id="8c930-117">If you have added yourself to the group and want to test the following code, you must log off the computer and log back on to be included in the group.</span></span>  
  
### <a name="to-demand-user-membership"></a><span data-ttu-id="8c930-118">Требование членства пользователя</span><span class="sxs-lookup"><span data-stu-id="8c930-118">To demand user membership</span></span>  
  
1.  <span data-ttu-id="8c930-119">Откройте файл кода [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], содержащий реализованный код контракта службы.</span><span class="sxs-lookup"><span data-stu-id="8c930-119">Open the [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] code file that contains the implemented service contract code.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="8c930-120">реализация контракта, в разделе [реализация контрактов службы](../../../docs/framework/wcf/implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="8c930-120"> implementing a contract, see [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
2.  <span data-ttu-id="8c930-121">Примените атрибут <xref:System.Security.Permissions.PrincipalPermissionAttribute> к каждому методу, доступ к которому необходимо ограничить определенной группой.</span><span class="sxs-lookup"><span data-stu-id="8c930-121">Apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to each method that must be restricted to a specific group.</span></span> <span data-ttu-id="8c930-122">Задайте для свойства <xref:System.Security.Permissions.SecurityAttribute.Action%2A> значение <xref:System.Security.Permissions.SecurityAction.Demand>, а для свойства <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> задайте имя группы.</span><span class="sxs-lookup"><span data-stu-id="8c930-122">Set the <xref:System.Security.Permissions.SecurityAttribute.Action%2A> property to <xref:System.Security.Permissions.SecurityAction.Demand> and the <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> property to the name of the group.</span></span> <span data-ttu-id="8c930-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="8c930-123">For example:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#1)]
     [!code-vb[c_PrincipalPermissionAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="8c930-124">Если применить атрибут <xref:System.Security.Permissions.PrincipalPermissionAttribute> к контракту, возникает исключение <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="8c930-124">If you apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to a contract a <xref:System.Security.SecurityException> will be thrown.</span></span> <span data-ttu-id="8c930-125">Этот атрибут может применяться только на уровне метода.</span><span class="sxs-lookup"><span data-stu-id="8c930-125">You can only apply the attribute at the method level.</span></span>  
  
## <a name="using-a-certificate-to-control-access-to-a-method"></a><span data-ttu-id="8c930-126">Использование сертификата для управления доступом к методу</span><span class="sxs-lookup"><span data-stu-id="8c930-126">Using a Certificate to Control Access to a Method</span></span>  
 <span data-ttu-id="8c930-127">Для управления доступом к методу можно также использовать класс `PrincipalPermissionAttribute`, если типом учетных данных клиента является сертификат.</span><span class="sxs-lookup"><span data-stu-id="8c930-127">You can also use the `PrincipalPermissionAttribute` class to control access to a method if the client credential type is a certificate.</span></span> <span data-ttu-id="8c930-128">Для этого необходимо иметь субъект и отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="8c930-128">To do this, you must have the certificate's subject and thumbprint.</span></span>  
  
 <span data-ttu-id="8c930-129">Проверить сертификат, для его свойства, в разделе [как: Просмотр сертификатов с помощью оснастки MMC](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="8c930-129">To examine a certificate for its properties, see [How to: View Certificates with the MMC Snap-in](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span> <span data-ttu-id="8c930-130">Значение отпечатка, в разделе [как: извлечение отпечатка сертификата](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="8c930-130">To find the thumbprint value, see [How to: Retrieve the Thumbprint of a Certificate](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
#### <a name="to-control-access-using-a-certificate"></a><span data-ttu-id="8c930-131">Управление доступом с помощью сертификата</span><span class="sxs-lookup"><span data-stu-id="8c930-131">To control access using a certificate</span></span>  
  
1.  <span data-ttu-id="8c930-132">Примените класс <xref:System.Security.Permissions.PrincipalPermissionAttribute> к методу, доступ к которому требуется ограничить.</span><span class="sxs-lookup"><span data-stu-id="8c930-132">Apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> class to the method you want to restrict access to.</span></span>  
  
2.  <span data-ttu-id="8c930-133">Задайте для действия атрибута значение <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8c930-133">Set the action of the attribute to <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.</span></span>  
  
3.  <span data-ttu-id="8c930-134">Задайте для свойства `Name` строку, состоящую из имени субъект и отпечатка сертификата.</span><span class="sxs-lookup"><span data-stu-id="8c930-134">Set the `Name` property to a string that consists of the subject name and the certificate's thumbprint.</span></span> <span data-ttu-id="8c930-135">Эти два значения должны разделяться точкой с запятой и пробелом, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8c930-135">Separate the two values with a semicolon and a space, as shown in the following example:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#2)]
     [!code-vb[c_PrincipalPermissionAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#2)]  
  
4.  <span data-ttu-id="8c930-136">Задайте для свойства <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> значение <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, как показано в следующем примере конфигурации:</span><span class="sxs-lookup"><span data-stu-id="8c930-136">Set the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> as shown in the following configuration example:</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="SvcBehavior1">  
      <serviceAuthorization principalPermissionMode="UseAspNetRoles" />  
      </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="8c930-137">Задание для этого параметра значения `UseAspNetRoles` означает, что свойство `Name` атрибута `PrincipalPermissionAttribute` будет использоваться для строкового сравнения.</span><span class="sxs-lookup"><span data-stu-id="8c930-137">Setting this value to `UseAspNetRoles` indicates that the `Name` property of the `PrincipalPermissionAttribute` will be used to perform a string comparison.</span></span> <span data-ttu-id="8c930-138">При использовании сертификата в качестве учетных данных клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] по умолчанию сцепляет общее имя и отпечаток сертификата с точкой с запятой, создавая уникальное значение для первичной идентификации клиента.</span><span class="sxs-lookup"><span data-stu-id="8c930-138">When a certificate is used as a client credential, by default [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] concatenates the certificate common name and the thumbprint with a semicolon to create a unique value for the client's primary identity.</span></span> <span data-ttu-id="8c930-139">Если в службе для режима `UseAspNetRoles` задано значение `PrincipalPermissionMode`, для определения прав доступа пользователя это значение первичной идентификации сравнивается со значением свойства `Name`.</span><span class="sxs-lookup"><span data-stu-id="8c930-139">With `UseAspNetRoles` set as the `PrincipalPermissionMode` on the service, this primary identity value is compared with the `Name` property value to determine the access rights of the user.</span></span>  
  
     <span data-ttu-id="8c930-140">При создании резидентной службы можно также задать свойство <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> в коде, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="8c930-140">Alternatively, when creating a self-hosted service, set the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property in code as shown in the following code:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#3)]
     [!code-vb[c_PrincipalPermissionAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8c930-141">См. также</span><span class="sxs-lookup"><span data-stu-id="8c930-141">See Also</span></span>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 <xref:System.Security.Permissions.SecurityAction.Demand>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>  
 [<span data-ttu-id="8c930-142">Авторизация доступа к операциям службы</span><span class="sxs-lookup"><span data-stu-id="8c930-142">Authorizing Access to Service Operations</span></span>](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="8c930-143">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="8c930-143">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="8c930-144">Реализация контрактов служб</span><span class="sxs-lookup"><span data-stu-id="8c930-144">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
