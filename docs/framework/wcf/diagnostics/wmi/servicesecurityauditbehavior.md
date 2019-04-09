---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 30679e1f67c6943bf674a6bbd8bf12be090765a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203513"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="2d451-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="2d451-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="2d451-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="2d451-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d451-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d451-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2d451-105">Методы</span><span class="sxs-lookup"><span data-stu-id="2d451-105">Methods</span></span>  
 <span data-ttu-id="2d451-106">Класс ServiceSecurityAuditBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="2d451-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2d451-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="2d451-107">Properties</span></span>  
 <span data-ttu-id="2d451-108">Класс ServiceSecurityAuditBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="2d451-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="2d451-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="2d451-109">AuditLogLocation</span></span>  
 <span data-ttu-id="2d451-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="2d451-110">Data type: string</span></span>  
  
 <span data-ttu-id="2d451-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="2d451-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2d451-112">Местоположение журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="2d451-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="2d451-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="2d451-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="2d451-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="2d451-114">Data type: string</span></span>  
  
 <span data-ttu-id="2d451-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="2d451-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2d451-116">Тип уровня проверки подлинности сообщений, используемый для записи в журнал событий аудита.</span><span class="sxs-lookup"><span data-stu-id="2d451-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="2d451-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="2d451-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="2d451-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="2d451-118">Data type: string</span></span>  
  
 <span data-ttu-id="2d451-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="2d451-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2d451-120">Типы событий авторизации, записываемых в журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="2d451-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="2d451-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="2d451-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="2d451-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="2d451-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="2d451-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="2d451-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2d451-124">Логическое значение, задающее поведение для подавления ошибок записи в журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="2d451-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d451-125">Требования</span><span class="sxs-lookup"><span data-stu-id="2d451-125">Requirements</span></span>  
  
|<span data-ttu-id="2d451-126">MOF</span><span class="sxs-lookup"><span data-stu-id="2d451-126">MOF</span></span>|<span data-ttu-id="2d451-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2d451-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2d451-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="2d451-128">Namespace</span></span>|<span data-ttu-id="2d451-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="2d451-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d451-130">См. также</span><span class="sxs-lookup"><span data-stu-id="2d451-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
