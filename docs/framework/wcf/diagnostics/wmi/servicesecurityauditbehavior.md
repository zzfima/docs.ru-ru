---
title: ServiceSecurityAuditBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ea9c04c201ff022fcea54b81a998b7020fb2a836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="2dca9-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="2dca9-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="2dca9-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="2dca9-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dca9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2dca9-104">Syntax</span></span>  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2dca9-105">Методы</span><span class="sxs-lookup"><span data-stu-id="2dca9-105">Methods</span></span>  
 <span data-ttu-id="2dca9-106">Класс ServiceSecurityAuditBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="2dca9-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2dca9-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="2dca9-107">Properties</span></span>  
 <span data-ttu-id="2dca9-108">Класс ServiceSecurityAuditBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="2dca9-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="2dca9-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="2dca9-109">AuditLogLocation</span></span>  
 <span data-ttu-id="2dca9-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="2dca9-110">Data type: string</span></span>  
  
 <span data-ttu-id="2dca9-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2dca9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2dca9-112">Местоположение журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="2dca9-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="2dca9-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="2dca9-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="2dca9-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="2dca9-114">Data type: string</span></span>  
  
 <span data-ttu-id="2dca9-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2dca9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2dca9-116">Тип уровня проверки подлинности сообщений, используемый для записи в журнал событий аудита.</span><span class="sxs-lookup"><span data-stu-id="2dca9-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="2dca9-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="2dca9-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="2dca9-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="2dca9-118">Data type: string</span></span>  
  
 <span data-ttu-id="2dca9-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2dca9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2dca9-120">Типы событий авторизации, записываемых в журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="2dca9-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="2dca9-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="2dca9-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="2dca9-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="2dca9-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="2dca9-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2dca9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2dca9-124">Логическое значение, задающее поведение для подавления ошибок записи в журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="2dca9-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dca9-125">Требования</span><span class="sxs-lookup"><span data-stu-id="2dca9-125">Requirements</span></span>  
  
|<span data-ttu-id="2dca9-126">MOF</span><span class="sxs-lookup"><span data-stu-id="2dca9-126">MOF</span></span>|<span data-ttu-id="2dca9-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2dca9-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2dca9-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="2dca9-128">Namespace</span></span>|<span data-ttu-id="2dca9-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="2dca9-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2dca9-130">См. также</span><span class="sxs-lookup"><span data-stu-id="2dca9-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
