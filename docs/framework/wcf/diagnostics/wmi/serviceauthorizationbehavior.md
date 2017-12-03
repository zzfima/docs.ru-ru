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
ms.openlocfilehash: fd22cd7e7783a67e7ad10371533eee680bd3af16
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="46acb-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="46acb-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="46acb-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="46acb-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46acb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46acb-104">Syntax</span></span>  
  
```  
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="46acb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="46acb-105">Methods</span></span>  
 <span data-ttu-id="46acb-106">Класс ServiceAuthorizationBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="46acb-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="46acb-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="46acb-107">Properties</span></span>  
 <span data-ttu-id="46acb-108">Класс ServiceAuthorizationBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="46acb-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="46acb-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="46acb-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="46acb-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="46acb-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="46acb-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="46acb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46acb-112">Значение, которое определяет, будет ли служба пытаться производить олицетворение при помощи учетных данных, содержащихся во входящем сообщении.</span><span class="sxs-lookup"><span data-stu-id="46acb-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="46acb-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="46acb-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="46acb-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="46acb-114">Data type: string</span></span>  
  
 <span data-ttu-id="46acb-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="46acb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46acb-116">Участник, используемый для выполнения операций на сервере.</span><span class="sxs-lookup"><span data-stu-id="46acb-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="46acb-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="46acb-117">RoleProvider</span></span>  
 <span data-ttu-id="46acb-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="46acb-118">Data type: string</span></span>  
  
 <span data-ttu-id="46acb-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="46acb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46acb-120">Имя поставщика ролей ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="46acb-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="46acb-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="46acb-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="46acb-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="46acb-122">Data type: string</span></span>  
  
 <span data-ttu-id="46acb-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="46acb-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46acb-124">Диспетчер авторизации, используемый для пользовательской авторизации.</span><span class="sxs-lookup"><span data-stu-id="46acb-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46acb-125">Требования</span><span class="sxs-lookup"><span data-stu-id="46acb-125">Requirements</span></span>  
  
|<span data-ttu-id="46acb-126">MOF</span><span class="sxs-lookup"><span data-stu-id="46acb-126">MOF</span></span>|<span data-ttu-id="46acb-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="46acb-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="46acb-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="46acb-128">Namespace</span></span>|<span data-ttu-id="46acb-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="46acb-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46acb-130">См. также</span><span class="sxs-lookup"><span data-stu-id="46acb-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
