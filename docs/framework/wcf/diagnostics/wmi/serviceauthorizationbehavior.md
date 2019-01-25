---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: 58eb2a9fd9017aaf9966644180936f5871e086d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613900"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="cc7f0-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="cc7f0-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="cc7f0-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="cc7f0-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc7f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc7f0-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cc7f0-105">Методы</span><span class="sxs-lookup"><span data-stu-id="cc7f0-105">Methods</span></span>  
 <span data-ttu-id="cc7f0-106">Класс ServiceAuthorizationBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="cc7f0-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cc7f0-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="cc7f0-107">Properties</span></span>  
 <span data-ttu-id="cc7f0-108">Класс ServiceAuthorizationBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="cc7f0-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="cc7f0-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="cc7f0-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="cc7f0-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="cc7f0-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="cc7f0-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="cc7f0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cc7f0-112">Значение, которое определяет, будет ли служба пытаться производить олицетворение при помощи учетных данных, содержащихся во входящем сообщении.</span><span class="sxs-lookup"><span data-stu-id="cc7f0-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="cc7f0-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="cc7f0-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="cc7f0-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="cc7f0-114">Data type: string</span></span>  
  
 <span data-ttu-id="cc7f0-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="cc7f0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cc7f0-116">Участник, используемый для выполнения операций на сервере.</span><span class="sxs-lookup"><span data-stu-id="cc7f0-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="cc7f0-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="cc7f0-117">RoleProvider</span></span>  
 <span data-ttu-id="cc7f0-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="cc7f0-118">Data type: string</span></span>  
  
 <span data-ttu-id="cc7f0-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="cc7f0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cc7f0-120">Имя поставщика ролей ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc7f0-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="cc7f0-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="cc7f0-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="cc7f0-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="cc7f0-122">Data type: string</span></span>  
  
 <span data-ttu-id="cc7f0-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="cc7f0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cc7f0-124">Диспетчер авторизации, используемый для пользовательской авторизации.</span><span class="sxs-lookup"><span data-stu-id="cc7f0-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc7f0-125">Требования</span><span class="sxs-lookup"><span data-stu-id="cc7f0-125">Requirements</span></span>  
  
|<span data-ttu-id="cc7f0-126">MOF</span><span class="sxs-lookup"><span data-stu-id="cc7f0-126">MOF</span></span>|<span data-ttu-id="cc7f0-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cc7f0-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cc7f0-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="cc7f0-128">Namespace</span></span>|<span data-ttu-id="cc7f0-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="cc7f0-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc7f0-130">См. также</span><span class="sxs-lookup"><span data-stu-id="cc7f0-130">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
