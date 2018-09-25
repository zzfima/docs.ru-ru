---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
author: BrucePerlerMS
ms.openlocfilehash: 8f43ee752830d95db6bbbdbe311b6d77735e31b5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070153"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="7999e-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="7999e-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="7999e-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="7999e-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7999e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7999e-104">Syntax</span></span>  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7999e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7999e-105">Methods</span></span>  
 <span data-ttu-id="7999e-106">Класс ServiceSecurityAuditBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="7999e-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7999e-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="7999e-107">Properties</span></span>  
 <span data-ttu-id="7999e-108">Класс ServiceSecurityAuditBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="7999e-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="7999e-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="7999e-109">AuditLogLocation</span></span>  
 <span data-ttu-id="7999e-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="7999e-110">Data type: string</span></span>  
  
 <span data-ttu-id="7999e-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7999e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7999e-112">Местоположение журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="7999e-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="7999e-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="7999e-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="7999e-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="7999e-114">Data type: string</span></span>  
  
 <span data-ttu-id="7999e-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7999e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7999e-116">Тип уровня проверки подлинности сообщений, используемый для записи в журнал событий аудита.</span><span class="sxs-lookup"><span data-stu-id="7999e-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="7999e-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="7999e-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="7999e-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="7999e-118">Data type: string</span></span>  
  
 <span data-ttu-id="7999e-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7999e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7999e-120">Типы событий авторизации, записываемых в журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="7999e-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="7999e-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="7999e-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="7999e-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="7999e-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="7999e-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7999e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7999e-124">Логическое значение, задающее поведение для подавления ошибок записи в журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="7999e-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7999e-125">Требования</span><span class="sxs-lookup"><span data-stu-id="7999e-125">Requirements</span></span>  
  
|<span data-ttu-id="7999e-126">MOF</span><span class="sxs-lookup"><span data-stu-id="7999e-126">MOF</span></span>|<span data-ttu-id="7999e-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7999e-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7999e-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="7999e-128">Namespace</span></span>|<span data-ttu-id="7999e-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="7999e-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7999e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="7999e-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
