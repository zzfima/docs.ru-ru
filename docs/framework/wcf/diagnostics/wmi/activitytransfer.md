---
title: ActivityTransfer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c1caf0ae27efce858328e5db88434253be61d50
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="activitytransfer"></a><span data-ttu-id="32f9c-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="32f9c-102">ActivityTransfer</span></span>
<span data-ttu-id="32f9c-103">Событие перенаправления действия</span><span class="sxs-lookup"><span data-stu-id="32f9c-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32f9c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32f9c-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="32f9c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="32f9c-105">Methods</span></span>  
 <span data-ttu-id="32f9c-106">Класс ActivityTransfer не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="32f9c-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="32f9c-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="32f9c-107">Properties</span></span>  
 <span data-ttu-id="32f9c-108">Класс ActivityTransfer имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="32f9c-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="32f9c-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="32f9c-109">ActivityID</span></span>  
  
-   <span data-ttu-id="32f9c-110">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="32f9c-110">Data type: object</span></span>  
    <span data-ttu-id="32f9c-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="32f9c-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="32f9c-112">Идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="32f9c-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="32f9c-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="32f9c-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="32f9c-114">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="32f9c-114">Data type: object</span></span>  
    <span data-ttu-id="32f9c-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="32f9c-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="32f9c-116">Связанный идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="32f9c-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32f9c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="32f9c-117">Requirements</span></span>  
  
|<span data-ttu-id="32f9c-118">MOF</span><span class="sxs-lookup"><span data-stu-id="32f9c-118">MOF</span></span>|<span data-ttu-id="32f9c-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="32f9c-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="32f9c-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="32f9c-120">Namespace</span></span>|<span data-ttu-id="32f9c-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="32f9c-121">Defined in root\ServiceModel.</span></span>|
