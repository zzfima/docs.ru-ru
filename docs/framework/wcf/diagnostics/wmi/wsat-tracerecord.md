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
ms.openlocfilehash: b4e701c2f0d669a04be7f7235c8ab1edb8ce1612
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="5f572-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="5f572-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="5f572-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="5f572-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f572-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f572-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5f572-105">Методы</span><span class="sxs-lookup"><span data-stu-id="5f572-105">Methods</span></span>  
 <span data-ttu-id="5f572-106">Класс WSAT_TraceRecord не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="5f572-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5f572-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="5f572-107">Properties</span></span>  
 <span data-ttu-id="5f572-108">Класс WSAT_TraceRecord имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="5f572-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="5f572-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="5f572-109">ActivityID</span></span>  
 <span data-ttu-id="5f572-110">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="5f572-110">Data type: object</span></span>  
<span data-ttu-id="5f572-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="5f572-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f572-112">ИД активности записи трассировки.</span><span class="sxs-lookup"><span data-stu-id="5f572-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="5f572-113">EventID</span><span class="sxs-lookup"><span data-stu-id="5f572-113">EventID</span></span>  
 <span data-ttu-id="5f572-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="5f572-114">Data type: sint32</span></span>  
<span data-ttu-id="5f572-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="5f572-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f572-116">ИД события записи трассировки.</span><span class="sxs-lookup"><span data-stu-id="5f572-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="5f572-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="5f572-117">TraceRecord</span></span>  
 <span data-ttu-id="5f572-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="5f572-118">Data type: string</span></span>  
<span data-ttu-id="5f572-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="5f572-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f572-120">Запись трассировки</span><span class="sxs-lookup"><span data-stu-id="5f572-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f572-121">Требования</span><span class="sxs-lookup"><span data-stu-id="5f572-121">Requirements</span></span>  
  
|<span data-ttu-id="5f572-122">MOF</span><span class="sxs-lookup"><span data-stu-id="5f572-122">MOF</span></span>|<span data-ttu-id="5f572-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="5f572-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5f572-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="5f572-124">Namespace</span></span>|<span data-ttu-id="5f572-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="5f572-125">Defined in root\ServiceModel</span></span>|
