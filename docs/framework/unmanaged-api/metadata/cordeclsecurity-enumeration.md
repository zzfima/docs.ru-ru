---
title: Перечисление CorDeclSecurity
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5409d1b89ba3e50c4ae17ed5aa6bf063cf6c93cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136972"
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="d4442-102">Перечисление CorDeclSecurity</span><span class="sxs-lookup"><span data-stu-id="d4442-102">CorDeclSecurity Enumeration</span></span>
<span data-ttu-id="d4442-103">Указывает действия безопасности, которые можно выполнить с помощью декларативной безопасности.</span><span class="sxs-lookup"><span data-stu-id="d4442-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4442-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4442-104">Syntax</span></span>  
  
```  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="d4442-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d4442-105">Members</span></span>  
  
|<span data-ttu-id="d4442-106">Член</span><span class="sxs-lookup"><span data-stu-id="d4442-106">Member</span></span>|<span data-ttu-id="d4442-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d4442-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="d4442-108">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d4442-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="d4442-109">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d4442-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="d4442-110">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d4442-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="d4442-111">Всем вызывающим объектам выше в стеке вызовов должно быть предоставлено разрешение, заданное текущим объектом разрешений.</span><span class="sxs-lookup"><span data-stu-id="d4442-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="d4442-112">Вызывающий код может получить доступ к ресурсу, определяемому текущим объектом разрешения, даже если вызывающим объектам выше в стеке вызовов не предоставлено разрешение на доступ к ресурсу</span><span class="sxs-lookup"><span data-stu-id="d4442-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="d4442-113">Для доступа к ресурсу, указанному текущим объектом разрешения запрещен вызывающим объектам, даже если они имеют разрешения на доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="d4442-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="d4442-114">Доступ можно получить только к ресурсам, указанным данным объектом разрешения, даже если коду предоставлено разрешение на доступ к другим ресурсам.</span><span class="sxs-lookup"><span data-stu-id="d4442-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="d4442-115">Непосредственный вызывающий оператор является обязательным, необходимо предоставить указанное разрешение для указанного периода времени.</span><span class="sxs-lookup"><span data-stu-id="d4442-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="d4442-116">Производного класса наследующему другой класс или переопределяющему метод, требуется получить указанное разрешение.</span><span class="sxs-lookup"><span data-stu-id="d4442-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="d4442-117">Вызывающий объект может запросить минимальные разрешения, необходимые для выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="d4442-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="d4442-118">Это действие может использоваться только в пределах сборки.</span><span class="sxs-lookup"><span data-stu-id="d4442-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="d4442-119">Вызывающий объект может запросить дополнительные разрешения, которые не являются обязательными (не требуется для запуска).</span><span class="sxs-lookup"><span data-stu-id="d4442-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="d4442-120">Этот запрос неявно отклоняет все прочие разрешения, не запрошенные специально.</span><span class="sxs-lookup"><span data-stu-id="d4442-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="d4442-121">Это действие может использоваться только в пределах сборки.</span><span class="sxs-lookup"><span data-stu-id="d4442-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="d4442-122">Не получат запрос вызывающей стороны для разрешения, которые могут быть неправильно использованы.</span><span class="sxs-lookup"><span data-stu-id="d4442-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="d4442-123">Это действие может использоваться только в пределах сборки.</span><span class="sxs-lookup"><span data-stu-id="d4442-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="d4442-124">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d4442-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="d4442-125">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d4442-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="d4442-126">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d4442-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="d4442-127">Указанное разрешение необходимо предоставить непосредственно вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="d4442-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="d4442-128">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d4442-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="d4442-129">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d4442-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="d4442-130">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d4442-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="d4442-131">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d4442-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="d4442-132">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d4442-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4442-133">Требования</span><span class="sxs-lookup"><span data-stu-id="d4442-133">Requirements</span></span>  
 <span data-ttu-id="d4442-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4442-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4442-135">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d4442-135">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="d4442-136">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d4442-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d4442-137">См. также</span><span class="sxs-lookup"><span data-stu-id="d4442-137">See also</span></span>

- [<span data-ttu-id="d4442-138">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="d4442-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
