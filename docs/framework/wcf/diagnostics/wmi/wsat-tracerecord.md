---
title: WSAT_TraceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d24f74d4086a5499d3bfd4ef6183d377528acc21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="3c7f5-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="3c7f5-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="3c7f5-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="3c7f5-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c7f5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c7f5-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3c7f5-105">Методы</span><span class="sxs-lookup"><span data-stu-id="3c7f5-105">Methods</span></span>  
 <span data-ttu-id="3c7f5-106">Класс WSAT_TraceRecord не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="3c7f5-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3c7f5-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="3c7f5-107">Properties</span></span>  
 <span data-ttu-id="3c7f5-108">Класс WSAT_TraceRecord имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="3c7f5-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="3c7f5-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="3c7f5-109">ActivityID</span></span>  
 <span data-ttu-id="3c7f5-110">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="3c7f5-110">Data type: object</span></span>  
<span data-ttu-id="3c7f5-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3c7f5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3c7f5-112">ИД активности записи трассировки.</span><span class="sxs-lookup"><span data-stu-id="3c7f5-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="3c7f5-113">EventID</span><span class="sxs-lookup"><span data-stu-id="3c7f5-113">EventID</span></span>  
 <span data-ttu-id="3c7f5-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="3c7f5-114">Data type: sint32</span></span>  
<span data-ttu-id="3c7f5-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3c7f5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3c7f5-116">ИД события записи трассировки.</span><span class="sxs-lookup"><span data-stu-id="3c7f5-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="3c7f5-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="3c7f5-117">TraceRecord</span></span>  
 <span data-ttu-id="3c7f5-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="3c7f5-118">Data type: string</span></span>  
<span data-ttu-id="3c7f5-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3c7f5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3c7f5-120">Запись трассировки</span><span class="sxs-lookup"><span data-stu-id="3c7f5-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c7f5-121">Требования</span><span class="sxs-lookup"><span data-stu-id="3c7f5-121">Requirements</span></span>  
  
|<span data-ttu-id="3c7f5-122">MOF</span><span class="sxs-lookup"><span data-stu-id="3c7f5-122">MOF</span></span>|<span data-ttu-id="3c7f5-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3c7f5-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3c7f5-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="3c7f5-124">Namespace</span></span>|<span data-ttu-id="3c7f5-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="3c7f5-125">Defined in root\ServiceModel</span></span>|
