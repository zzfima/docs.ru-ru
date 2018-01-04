---
title: Binding2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6553d1e1c030a30eed74ff81d3e07e28a9f25b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="binding"></a><span data-ttu-id="1fef7-102">Привязка</span><span class="sxs-lookup"><span data-stu-id="1fef7-102">Binding</span></span>
<span data-ttu-id="1fef7-103">wmi Binding</span><span class="sxs-lookup"><span data-stu-id="1fef7-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fef7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fef7-104">Syntax</span></span>  
  
```  
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1fef7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="1fef7-105">Methods</span></span>  
 <span data-ttu-id="1fef7-106">Класс Binding не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="1fef7-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1fef7-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="1fef7-107">Properties</span></span>  
 <span data-ttu-id="1fef7-108">Класс Binding имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="1fef7-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="1fef7-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="1fef7-109">BindingElements</span></span>  
 <span data-ttu-id="1fef7-110">Тип данных: массив BindingElement</span><span class="sxs-lookup"><span data-stu-id="1fef7-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="1fef7-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1fef7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fef7-112">Коллекция элементов привязки, реализованных привязкой.</span><span class="sxs-lookup"><span data-stu-id="1fef7-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="1fef7-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="1fef7-113">CloseTimeout</span></span>  
 <span data-ttu-id="1fef7-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="1fef7-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="1fef7-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1fef7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fef7-116">Интервал времени, предусмотренный для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="1fef7-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="1fef7-117">name</span><span class="sxs-lookup"><span data-stu-id="1fef7-117">Name</span></span>  
 <span data-ttu-id="1fef7-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1fef7-118">Data type: string</span></span>  
  
 <span data-ttu-id="1fef7-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1fef7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fef7-120">Имя привязки.</span><span class="sxs-lookup"><span data-stu-id="1fef7-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="1fef7-121">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="1fef7-121">Namespace</span></span>  
 <span data-ttu-id="1fef7-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1fef7-122">Data type: string</span></span>  
  
 <span data-ttu-id="1fef7-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1fef7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fef7-124">Пространство имен XML привязки.</span><span class="sxs-lookup"><span data-stu-id="1fef7-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="1fef7-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="1fef7-125">OpenTimeout</span></span>  
 <span data-ttu-id="1fef7-126">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="1fef7-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="1fef7-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1fef7-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fef7-128">Интервал времени, предусмотренный для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="1fef7-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="1fef7-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="1fef7-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="1fef7-130">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="1fef7-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="1fef7-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1fef7-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fef7-132">Интервал времени, предусмотренный для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="1fef7-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="1fef7-133">Схема</span><span class="sxs-lookup"><span data-stu-id="1fef7-133">Scheme</span></span>  
 <span data-ttu-id="1fef7-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1fef7-134">Data type: string</span></span>  
  
 <span data-ttu-id="1fef7-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1fef7-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fef7-136">Схема транспорта универсальных кодов ресурсов (URI), которая используется производствами каналов и прослушивателей, созданными привязкой.</span><span class="sxs-lookup"><span data-stu-id="1fef7-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="1fef7-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="1fef7-137">SendTimeout</span></span>  
 <span data-ttu-id="1fef7-138">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="1fef7-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="1fef7-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="1fef7-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1fef7-140">Интервал времени, предусмотренный для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="1fef7-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fef7-141">Требования</span><span class="sxs-lookup"><span data-stu-id="1fef7-141">Requirements</span></span>  
  
|<span data-ttu-id="1fef7-142">MOF</span><span class="sxs-lookup"><span data-stu-id="1fef7-142">MOF</span></span>|<span data-ttu-id="1fef7-143">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1fef7-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1fef7-144">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="1fef7-144">Namespace</span></span>|<span data-ttu-id="1fef7-145">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="1fef7-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1fef7-146">См. также</span><span class="sxs-lookup"><span data-stu-id="1fef7-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>
