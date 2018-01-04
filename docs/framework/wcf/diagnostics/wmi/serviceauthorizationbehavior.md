---
title: ServiceAuthorizationBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62f3e32e886f49ac8dde6af5c37a4e57373c9576
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="62f75-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="62f75-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="62f75-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="62f75-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62f75-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62f75-104">Syntax</span></span>  
  
```  
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="62f75-105">Методы</span><span class="sxs-lookup"><span data-stu-id="62f75-105">Methods</span></span>  
 <span data-ttu-id="62f75-106">Класс ServiceAuthorizationBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="62f75-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="62f75-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="62f75-107">Properties</span></span>  
 <span data-ttu-id="62f75-108">Класс ServiceAuthorizationBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="62f75-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="62f75-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="62f75-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="62f75-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="62f75-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="62f75-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="62f75-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62f75-112">Значение, которое определяет, будет ли служба пытаться производить олицетворение при помощи учетных данных, содержащихся во входящем сообщении.</span><span class="sxs-lookup"><span data-stu-id="62f75-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="62f75-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="62f75-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="62f75-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="62f75-114">Data type: string</span></span>  
  
 <span data-ttu-id="62f75-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="62f75-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62f75-116">Участник, используемый для выполнения операций на сервере.</span><span class="sxs-lookup"><span data-stu-id="62f75-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="62f75-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="62f75-117">RoleProvider</span></span>  
 <span data-ttu-id="62f75-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="62f75-118">Data type: string</span></span>  
  
 <span data-ttu-id="62f75-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="62f75-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62f75-120">Имя поставщика ролей ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="62f75-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="62f75-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="62f75-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="62f75-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="62f75-122">Data type: string</span></span>  
  
 <span data-ttu-id="62f75-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="62f75-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62f75-124">Диспетчер авторизации, используемый для пользовательской авторизации.</span><span class="sxs-lookup"><span data-stu-id="62f75-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62f75-125">Требования</span><span class="sxs-lookup"><span data-stu-id="62f75-125">Requirements</span></span>  
  
|<span data-ttu-id="62f75-126">MOF</span><span class="sxs-lookup"><span data-stu-id="62f75-126">MOF</span></span>|<span data-ttu-id="62f75-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="62f75-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="62f75-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="62f75-128">Namespace</span></span>|<span data-ttu-id="62f75-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="62f75-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62f75-130">См. также</span><span class="sxs-lookup"><span data-stu-id="62f75-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
