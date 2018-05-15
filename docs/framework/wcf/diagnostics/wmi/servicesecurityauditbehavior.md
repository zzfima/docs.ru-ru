---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 3adc721dd8ad0fb706e172373e5da70fe6032db6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="d608d-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="d608d-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="d608d-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="d608d-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d608d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d608d-104">Syntax</span></span>  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d608d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d608d-105">Methods</span></span>  
 <span data-ttu-id="d608d-106">Класс ServiceSecurityAuditBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="d608d-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d608d-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="d608d-107">Properties</span></span>  
 <span data-ttu-id="d608d-108">Класс ServiceSecurityAuditBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="d608d-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="d608d-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="d608d-109">AuditLogLocation</span></span>  
 <span data-ttu-id="d608d-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="d608d-110">Data type: string</span></span>  
  
 <span data-ttu-id="d608d-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d608d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d608d-112">Местоположение журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="d608d-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="d608d-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="d608d-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="d608d-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="d608d-114">Data type: string</span></span>  
  
 <span data-ttu-id="d608d-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d608d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d608d-116">Тип уровня проверки подлинности сообщений, используемый для записи в журнал событий аудита.</span><span class="sxs-lookup"><span data-stu-id="d608d-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="d608d-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="d608d-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="d608d-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="d608d-118">Data type: string</span></span>  
  
 <span data-ttu-id="d608d-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d608d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d608d-120">Типы событий авторизации, записываемых в журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="d608d-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="d608d-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="d608d-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="d608d-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="d608d-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="d608d-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d608d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d608d-124">Логическое значение, задающее поведение для подавления ошибок записи в журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="d608d-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d608d-125">Требования</span><span class="sxs-lookup"><span data-stu-id="d608d-125">Requirements</span></span>  
  
|<span data-ttu-id="d608d-126">MOF</span><span class="sxs-lookup"><span data-stu-id="d608d-126">MOF</span></span>|<span data-ttu-id="d608d-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d608d-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d608d-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="d608d-128">Namespace</span></span>|<span data-ttu-id="d608d-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="d608d-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d608d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d608d-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
