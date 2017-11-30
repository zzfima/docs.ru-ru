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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: eb02a02557a88bf53ca1a8e5b30fe66d6995e545
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="63289-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="63289-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="63289-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="63289-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63289-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63289-104">Syntax</span></span>  
  
```  
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="63289-105">Методы</span><span class="sxs-lookup"><span data-stu-id="63289-105">Methods</span></span>  
 <span data-ttu-id="63289-106">Класс ServiceAuthorizationBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="63289-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="63289-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="63289-107">Properties</span></span>  
 <span data-ttu-id="63289-108">Класс ServiceAuthorizationBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="63289-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="63289-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="63289-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="63289-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="63289-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="63289-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="63289-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63289-112">Значение, которое определяет, будет ли служба пытаться производить олицетворение при помощи учетных данных, содержащихся во входящем сообщении.</span><span class="sxs-lookup"><span data-stu-id="63289-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="63289-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="63289-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="63289-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="63289-114">Data type: string</span></span>  
  
 <span data-ttu-id="63289-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="63289-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63289-116">Участник, используемый для выполнения операций на сервере.</span><span class="sxs-lookup"><span data-stu-id="63289-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="63289-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="63289-117">RoleProvider</span></span>  
 <span data-ttu-id="63289-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="63289-118">Data type: string</span></span>  
  
 <span data-ttu-id="63289-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="63289-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63289-120">Имя поставщика ролей ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="63289-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="63289-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="63289-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="63289-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="63289-122">Data type: string</span></span>  
  
 <span data-ttu-id="63289-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="63289-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63289-124">Диспетчер авторизации, используемый для пользовательской авторизации.</span><span class="sxs-lookup"><span data-stu-id="63289-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63289-125">Требования</span><span class="sxs-lookup"><span data-stu-id="63289-125">Requirements</span></span>  
  
|<span data-ttu-id="63289-126">MOF</span><span class="sxs-lookup"><span data-stu-id="63289-126">MOF</span></span>|<span data-ttu-id="63289-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="63289-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="63289-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="63289-128">Namespace</span></span>|<span data-ttu-id="63289-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="63289-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63289-130">См. также</span><span class="sxs-lookup"><span data-stu-id="63289-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
