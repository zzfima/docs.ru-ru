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
ms.workload: dotnet
ms.openlocfilehash: 7f3db50a32fabc117c79eef5ac086a7798f86ed3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="activitytransfer"></a><span data-ttu-id="f6ebb-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="f6ebb-102">ActivityTransfer</span></span>
<span data-ttu-id="f6ebb-103">Событие перенаправления действия</span><span class="sxs-lookup"><span data-stu-id="f6ebb-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6ebb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6ebb-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f6ebb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f6ebb-105">Methods</span></span>  
 <span data-ttu-id="f6ebb-106">Класс ActivityTransfer не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="f6ebb-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f6ebb-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="f6ebb-107">Properties</span></span>  
 <span data-ttu-id="f6ebb-108">Класс ActivityTransfer имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="f6ebb-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="f6ebb-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="f6ebb-109">ActivityID</span></span>  
  
-   <span data-ttu-id="f6ebb-110">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="f6ebb-110">Data type: object</span></span>  
    <span data-ttu-id="f6ebb-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6ebb-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="f6ebb-112">Идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="f6ebb-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="f6ebb-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="f6ebb-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="f6ebb-114">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="f6ebb-114">Data type: object</span></span>  
    <span data-ttu-id="f6ebb-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f6ebb-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="f6ebb-116">Связанный идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="f6ebb-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6ebb-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f6ebb-117">Requirements</span></span>  
  
|<span data-ttu-id="f6ebb-118">MOF</span><span class="sxs-lookup"><span data-stu-id="f6ebb-118">MOF</span></span>|<span data-ttu-id="f6ebb-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f6ebb-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f6ebb-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="f6ebb-120">Namespace</span></span>|<span data-ttu-id="f6ebb-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="f6ebb-121">Defined in root\ServiceModel.</span></span>|
