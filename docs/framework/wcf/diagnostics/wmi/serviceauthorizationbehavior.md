---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: c916d0820a1eae333384deab7b0619abfbdc8167
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374304"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="affb2-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="affb2-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="affb2-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="affb2-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="affb2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="affb2-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="affb2-105">Методы</span><span class="sxs-lookup"><span data-stu-id="affb2-105">Methods</span></span>  
 <span data-ttu-id="affb2-106">Класс ServiceAuthorizationBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="affb2-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="affb2-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="affb2-107">Properties</span></span>  
 <span data-ttu-id="affb2-108">Класс ServiceAuthorizationBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="affb2-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="affb2-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="affb2-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="affb2-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="affb2-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="affb2-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="affb2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="affb2-112">Значение, которое определяет, будет ли служба пытаться производить олицетворение при помощи учетных данных, содержащихся во входящем сообщении.</span><span class="sxs-lookup"><span data-stu-id="affb2-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="affb2-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="affb2-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="affb2-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="affb2-114">Data type: string</span></span>  
  
 <span data-ttu-id="affb2-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="affb2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="affb2-116">Участник, используемый для выполнения операций на сервере.</span><span class="sxs-lookup"><span data-stu-id="affb2-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="affb2-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="affb2-117">RoleProvider</span></span>  
 <span data-ttu-id="affb2-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="affb2-118">Data type: string</span></span>  
  
 <span data-ttu-id="affb2-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="affb2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="affb2-120">Имя поставщика ролей ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="affb2-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="affb2-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="affb2-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="affb2-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="affb2-122">Data type: string</span></span>  
  
 <span data-ttu-id="affb2-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="affb2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="affb2-124">Диспетчер авторизации, используемый для пользовательской авторизации.</span><span class="sxs-lookup"><span data-stu-id="affb2-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="affb2-125">Требования</span><span class="sxs-lookup"><span data-stu-id="affb2-125">Requirements</span></span>  
  
|<span data-ttu-id="affb2-126">MOF</span><span class="sxs-lookup"><span data-stu-id="affb2-126">MOF</span></span>|<span data-ttu-id="affb2-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="affb2-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="affb2-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="affb2-128">Namespace</span></span>|<span data-ttu-id="affb2-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="affb2-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="affb2-130">См. также</span><span class="sxs-lookup"><span data-stu-id="affb2-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
